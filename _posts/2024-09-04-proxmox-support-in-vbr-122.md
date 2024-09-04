---
title: "Proxmox Support in VBR 12.2: The VMware Exodus Has a Safety Net"
date: 2024-09-04 20:00:00 -0400
categories: [Veeam]
tags: [veeam, proxmox, vmware, broadcom, vcsp, backup]
---

Veeam Backup & Replication v12.2 shipped last week. The feature that jumped off the page for me was Proxmox VE support.

## Background

Since Broadcom closed the VMware deal, the licensing changes have pushed a lot of organizations, especially SMBs and service providers, to look at alternatives. Proxmox has emerged as one of the most popular landing spots. It's open source, KVM-based, and has been quietly maturing for years.

The problem was backup. If you're a Veeam shop running VMware and you start migrating workloads to Proxmox, your backup strategy just broke. Veeam didn't support Proxmox. So you were either running a second backup product alongside Veeam or going without proper protection for those workloads. Neither option is great.

## The Proxmox integration

Proxmox integration with immutable backup support, granular restores, and full VM restores, including cross-platform restores from other hypervisors. That last part is the important one: you can restore a VMware backup *to* Proxmox. Back up on VMware, restore on Proxmox, validate everything works, cut over. That's a real migration path.

For partners who've been watching their VMware licensing costs go up, being able to build on Proxmox without losing Veeam backup coverage removes one of the bigger blockers.

## Early days

We're already getting questions from partners about Proxmox backup architecture: agent-based vs. agentless, snapshot behavior on KVM, storage compatibility. It's early and the knowledge base is thin. If you're deploying this in production, expect to hit some edge cases nobody's documented yet.

I've been spinning up Proxmox in my home lab to get ahead of the support cases I know are coming. If you're in VCSP support and you're not already familiar with it, now's the time. Don't wait for the first production escalation to start learning.

## Everything Else

v12.2 also brought Nutanix AHV improvements, MongoDB backup support, and RBAC enhancements. But Proxmox is the one that matters right now given what's happening in the VMware world.
