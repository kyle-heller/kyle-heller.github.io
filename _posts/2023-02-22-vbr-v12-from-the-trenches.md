---
title: "VBR v12 from the Trenches: What I'm Telling Our VCSP Partners"
date: 2023-02-22 20:15:00 -0500
categories: [Veeam]
tags: [veeam, vbr, v12, vcsp, backup]
---

Veeam Backup & Replication v12 just went GA and it's a monster release with 500+ new features and enhancements. I've been digging through the release notes and testing in the lab, and here's what actually matters from a VCSP support perspective.

## Direct-to-Object Storage Changes Everything for Partners

This is the headliner and it deserves to be. Partners can now back up directly to object storage without an intermediate repository. For service providers building BaaS offerings on top of S3-compatible storage, this eliminates an entire tier of infrastructure that was previously required.

From a support standpoint, I'm cautiously optimistic. Fewer moving parts means fewer things to break. But it also means a new failure domain. If the object storage target has latency issues or throttling, the backup job itself is now directly affected rather than the copy job. I expect we'll see a new category of support cases around object storage connectivity and performance that we haven't dealt with before.

## Immutability Gets Serious

Trusted immutability across every workload was long overdue. With ransomware cases coming through support on a near-weekly basis, having native immutability options for hardened Linux repositories, object storage, and partner-hosted repositories gives our partners a real answer when their customers ask "are my backups safe from encryption?"

The answer is now "yes" in a way it wasn't before.

## VeeaMover Will Save Me Hours of Escalations

I really cannot overstate how much time my team has spent helping partners manually migrate backup data between repositories while preserving job associations. It was always possible but it involved workarounds, manual configuration edits, and a lot of hand-holding.

VeeaMover turns that into a few clicks. This single feature will probably eliminate an entire class of support cases for us.

## CDP for Cloud Connect and VCD

Continuous Data Protection coming to Cloud Connect and VMware Cloud Director is huge for our VCSP partners specifically. This unlocks real DRaaS offerings with low RPOs that were previously only available in direct-connect scenarios. Partners have been asking for this for years.

## What I'm Watching For

Every major release brings a wave of upgrade-related support cases. v12 is a significant architectural change with the object storage backend, so I'm expecting a bumpier upgrade cycle than v11. If you're a partner reading this: test your upgrade in a lab environment first, verify your object storage connectivity, and don't upgrade production on a Friday. Please. I'm asking nicely.

I'll probably write more once I've seen the first few weeks of real-world deployments. Or I'll be too busy with support cases to write anything. We'll see.
