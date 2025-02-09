---
title: "Terraform Azurerm Backend: The 'Key' Field That Will Ruin Your Morning"
date: 2025-02-09 09:15:00 -0500
categories: [Infrastructure as Code, Terraform]
tags: [terraform, azure, remote-state, troubleshooting]
---

Quick one. This got me on a Friday afternoon and I don't want it to bite you.

When configuring the `azurerm` backend for Terraform remote state in Azure Storage, you have a `key` field:

```hcl
terraform {
  backend "azurerm" {
    resource_group_name  = "rg-terraform-state"
    storage_account_name = "stterraformstate"
    container_name       = "tfstate"
    key                  = "dev.terraform.tfstate"
  }
}
```

That `key` is the blob name in the storage container. It's how Terraform identifies *which* state file to use.

## The Mistake

I was setting up separate dev and prod environments. Copied my backend config, updated the resource group and storage account... but forgot to change the `key`.

Both environments pointed to `dev.terraform.tfstate`.

Running `terraform plan` on prod showed a plan to *destroy* all the dev resources and create the prod ones. Because Terraform thought the dev state *was* the prod state, and everything in dev didn't match the prod config.

I caught it on the plan. If I hadn't been paying attention, `terraform apply` would have nuked dev.

## The Fix

Obviously, use different keys:

```hcl
# Dev
key = "dev.terraform.tfstate"

# Prod
key = "prod.terraform.tfstate"
```

But the real fix is to stop hand-editing backend configs. Use partial backend configuration and pass the key at init time:

```bash
terraform init -backend-config="key=dev.terraform.tfstate"
```

Or better yet, use a `.backend.hcl` file per environment:

```hcl
# environments/dev/backend.hcl
key = "dev.terraform.tfstate"
```

```bash
terraform init -backend-config=environments/dev/backend.hcl
```

Now your backend key lives next to the rest of your environment config, and you can't accidentally cross the streams.

Anyway. Check your `key` fields. Especially if you just copy-pasted a backend config block from another environment. Don't ask me how I know.
