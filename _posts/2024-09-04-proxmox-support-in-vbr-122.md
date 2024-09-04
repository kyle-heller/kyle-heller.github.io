---
title: "Proxmox Support in VBR 12.2: The VMware Exodus Has a Safety Net"
date: 2024-09-04 20:00:00 -0400
categories: [Veeam]
tags: [veeam, proxmox, vmware, broadcom, vcsp, backup]
---

Veeam Backup & Replication v12.2 shipped last week and the feature that jumped off the page for me was Proxmox VE support. If you've been paying attention to the virtualization market since the Broadcom acquisition of VMware, you already know where this is going.

## The Context

Since Broadcom closed the VMware deal, licensing changes have pushed a significant number of organizations, especially SMBs and service providers, to evaluate alternatives. Proxmox VE has emerged as one of the most popular landing spots. It's open source, it's KVM-based, and it's been quietly maturing for years.

The problem was backup. If you're a Veeam shop running VMware and you migrate workloads to Proxmox, your backup strategy just broke. Veeam didn't support Proxmox, so you were either running a second backup product in parallel or going without enterprise-grade protection for those workloads.

## What 12.2 Delivers

The new Proxmox integration includes immutable backup support, granular restores, and full VM restores, including cross-platform restores from other hypervisors. That last part is key: you can restore a VMware backup *to* Proxmox. For partners planning a migration, that's your safety net. Back up on VMware, restore on Proxmox, validate, cut over.

From a VCSP perspective, this opens up a new market. Partners who are building hosting platforms on Proxmox can now offer Veeam-backed BaaS to their customers without a VMware dependency. That's a meaningful cost reduction for partners whose licensing just got significantly more expensive.

## What I'm Seeing in Support

We're already getting questions from partners about Proxmox backup architecture: agent-based vs. agentless, snapshot behavior on KVM, storage compatibility. It's early days and the knowledge base is thin. If you're deploying this in production, expect to be one of the first to hit edge cases.

I've been spinning up Proxmox in my home lab to get ahead of the support cases I know are coming. If you're in VCSP support and you're not already familiar with Proxmox, now is the time.

## The Bigger Picture

v12.2 also brought Nutanix AHV improvements, MongoDB backup support, and RBAC enhancements. But the Proxmox addition is the strategic one. Veeam is making it clear that they're not tied to any single hypervisor ecosystem, which is exactly the right message at exactly the right time.
