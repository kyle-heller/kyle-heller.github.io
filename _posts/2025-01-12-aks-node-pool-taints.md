---
title: "Why Your AKS Node Pool Taints Keep Getting Wiped on Every Apply"
date: 2025-01-12 20:30:00 -0500
categories: [Infrastructure as Code, Terraform]
tags: [terraform, aks, azure, node-pools, troubleshooting]
---

I ran into this one while building out Terraform modules for AKS cluster provisioning, and it took me way longer than I'd like to admit to figure out what was happening.

I had a dedicated node pool for monitoring workloads: Prometheus, Grafana, the usual suspects. I applied a taint so only monitoring pods would schedule there:

```hcl
resource "azurerm_kubernetes_cluster_node_pool" "monitoring" {
  name                  = "monitoring"
  kubernetes_cluster_id = azurerm_kubernetes_cluster.main.id
  vm_size               = "Standard_D4s_v3"
  node_count            = 2

  node_taints = ["workload=monitoring:NoSchedule"]
}
```

First apply: perfect. Taints show up. Pods schedule where they should.

Second apply: Terraform wants to update the node pool. No changes in my code. What?

## The Problem

The AKS API returns taints in a slightly different format than what Terraform sends. Specifically, the API normalizes the taint string, and the `azurerm` provider does a simple string comparison. Every `plan` sees a "change" and wants to re-apply.

This is a known quirk. It doesn't always happen. It depends on your provider version and the specific taint format.

## The Fix

Pin your taint format to exactly match what the API returns. In my case, that meant:

```hcl
node_taints = ["workload=monitoring:NoSchedule"]
```

If that still drifts, add a `lifecycle` block to ignore it:

```hcl
lifecycle {
  ignore_changes = [node_taints]
}
```

Yes, it feels wrong to ignore taints in Terraform. But if you're managing taints via `kubectl` or a GitOps tool anyway, this is actually the cleaner approach. Let Terraform own the node pool lifecycle and let your K8s tooling own the scheduling rules.
