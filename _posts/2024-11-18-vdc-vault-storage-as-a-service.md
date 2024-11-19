---
title: "Veeam Data Cloud Vault: What Storage-as-a-Service Tells Us About Veeam's Platform Ambitions"
date: 2024-11-18 21:30:00 -0500
categories: [Veeam, Cloud]
tags: [veeam, vdc, veeam-data-cloud, vault, azure, cloud-infrastructure, storage]
---

Veeam announced updates to VDC Vault at Microsoft Ignite: two new pricing tiers, flat per-TB pricing, and direct integration with the VBR console. On the surface it's a storage product announcement. But I keep thinking about what's going on underneath.

## What It Is

VDC Vault is managed immutable storage built on Azure Blob. You provision it from the Veeam console without touching the Azure portal. No storage account config, no fiddling with access keys, no immutability policy setup. Flat per-TB pricing with reads, writes, and egress included. If you've ever gotten an unexpected Azure egress bill (I have, more than once), you understand why that last part matters.

## The Part I Find Interesting

When a customer provisions a Vault, they're not getting a raw Azure storage account. They're getting a Veeam-managed resource that happens to run on Azure infrastructure. Veeam built an abstraction layer that handles provisioning, access control, immutability enforcement, encryption, monitoring, and billing. Per tenant, at scale.

Somebody at Veeam is running a multi-tenant storage platform with automated lifecycle management and cost modeling that absorbs Azure's variable pricing into a flat rate. The API layer connecting the on-prem VBR console to the cloud control plane is its own engineering challenge.

This is the kind of infrastructure work I find genuinely interesting. I don't care that much about the product itself. I care about the problems the team building it has to solve: tenant isolation that actually works, and a cost model that absorbs Azure's variable pricing into something predictable. That's the work I want to do.

## For Partners

For partners who've been maintaining their own offsite storage (racking drives, managing replication, monitoring capacity), Vault is worth evaluating as a replacement. It's just another backup target from VBR's perspective, but one you don't have to manage. The math on operational overhead alone might make it worthwhile, especially if you're a small team already stretched thin.
