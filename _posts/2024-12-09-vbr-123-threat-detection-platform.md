---
title: "VBR 12.3: When Your Backup Server Becomes a Threat Detection Platform"
date: 2024-12-09 19:45:00 -0500
categories: [Veeam]
tags: [veeam, vbr, v12.3, threat-hunter, vcsp, security, backup]
---

Veeam Backup & Replication 12.3 dropped this week and they're calling it a "point release." I don't know who decided that. It is not a point release.

## Threat Hunter and IoC Detection

The two big security additions: Threat Hunter scans backup content for malware using ML and heuristic analysis, with signatures updated multiple times daily. Indicators of Compromise detection watches for known attacker tools showing up in your protected machines' file systems.

From a support perspective, I expect this means a new category of cases: false positive tuning, alert fatigue, partners wondering why Threat Hunter flagged some legitimate admin tool. That's going to be a learning curve for everyone. But honestly, I'd much rather help someone configure threat detection than help them recover from ransomware. I've done both. The ransomware calls are worse.

## Entra ID Backup in VDC

The one that made me pay attention: Microsoft Entra ID backup in Veeam Data Cloud. If your Entra ID tenant gets compromised or someone fat-fingers a conditional access policy, your recovery options have historically been somewhere between "painful" and "rebuild everything from scratch." Having an actual backup of your identity layer is one of those things that seems obvious in hindsight.

## Windows Server 2025 and Vault Integration

Full support for Windows Server 2025 as a guest OS and Hyper-V 2025. Also, 12.3 streamlines the VDC Vault integration. You can provision and monitor Vault storage directly from the VBR console now. Combined with the flat pricing announced at Ignite, setting up offsite immutable storage has gotten pretty frictionless.

## If you're upgrading

If you're a partner: upgrade your lab first. Test Threat Hunter against your existing backup data before you roll it out to production. Read the release notes. All of them. There's a lot packed into a "point release."
