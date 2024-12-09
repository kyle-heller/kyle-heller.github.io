---
title: "VBR 12.3: When Your Backup Server Becomes a Threat Detection Platform"
date: 2024-12-09 19:45:00 -0500
categories: [Veeam]
tags: [veeam, vbr, v12.3, threat-hunter, vcsp, security, backup]
---

Veeam Backup & Replication 12.3 dropped this week and they're calling it a "point release." I don't know who decided that. It is not a point release. This is a feature-packed update that fundamentally expands what a backup server does.

## Threat Hunter and IoC Detection

The two headline security features: Veeam Threat Hunter scans backup content for malware using machine learning and heuristic analysis, faster than traditional AV, with signatures updated multiple times daily. Indicators of Compromise detection flags the sudden appearance of known hacker tools in your protected machines' file systems.

For VCSP partners, this changes the conversation with end customers. You're no longer selling "we back up your data." You're selling "we back up your data *and* we tell you if something is living in it that shouldn't be." That's a security value proposition, not just a data protection one.

From a support standpoint, I expect we'll see new case types around Threat Hunter false positives and IoC alerting configuration. Partners will need guidance on tuning these features for their specific environments. But I'd rather support partners configuring threat detection than support partners recovering from ransomware.

## Windows Server 2025 and Entra ID Support

The platform support additions are significant for Azure-heavy shops. Full support for Windows Server 2025 as a guest OS, Hyper-V 2025, and the one that made me sit up: Microsoft Entra ID backup in Veeam Data Cloud.

As someone with Azure certifications working in cloud infrastructure support, Entra ID protection has been a glaring gap. Identity is the control plane of modern cloud infrastructure. If your Entra ID tenant is compromised or misconfigured and you don't have a backup, your recovery options are painful. This fills that gap.

## The VDC Vault Integration

12.3 also streamlines the Veeam Data Cloud Vault integration. Partners can now provision and monitor Vault storage directly from the VBR console. Combined with the flat per-TB pricing announced at Ignite, this makes offsite immutable storage almost frictionless to set up.

## What VCSP Partners Should Do

Upgrade your lab. Test Threat Hunter against your existing backup data. Evaluate the VDC Vault integration as a replacement for self-managed offsite storage. And start thinking about how to position threat detection capabilities in your service offerings. This is the kind of feature that justifies a premium tier.

Don't let the version number fool you.
