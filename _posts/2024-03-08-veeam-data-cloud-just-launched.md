---
title: "Veeam Data Cloud Just Launched and I Have Thoughts"
date: 2024-03-08 21:00:00 -0500
categories: [Veeam, Cloud]
tags: [veeam, vdc, veeam-data-cloud, azure, baas, cloud-infrastructure]
---

Veeam just announced Veeam Data Cloud, a fully managed BaaS offering built on Azure for Microsoft 365 and Azure workloads. I've spent five years supporting partners who deliver exactly this kind of service, so this landed a little differently for me than it might for most people.

## What It Is

VDC is Veeam's first real SaaS play. Instead of selling software that partners install, manage, and maintain, Veeam is now selling the outcome directly: backup and recovery as a managed service. Software, infrastructure, storage. All bundled, all Veeam's responsibility, all running on Azure.

## The Awkward Part

I support cloud service providers. These partners built businesses around hosting Veeam infrastructure and selling backup services to their customers. VDC is, in some ways, Veeam competing with its own partner ecosystem.

That's not necessarily as dramatic as it sounds. Large enterprises increasingly want managed services directly from the vendor. Partners who provide real value (managed services, multi-vendor support, custom configurations) will be fine. Partners who were basically reselling Veeam with a thin margin on top have a harder road ahead. That's been the case for a while though; VDC just makes it more visible.

My partners are already asking questions. I don't have great answers yet.

## The Part That Actually Excites Me

Forget the product for a second. Think about what VDC requires under the hood. Somebody has to automate tenant provisioning. There's per-customer storage with immutability guarantees. A control plane managing backup policies for thousands of tenants. CI/CD that deploys updates without downtime. Monitoring that catches problems before customers do.

Somebody at Veeam is building all of that: Kubernetes clusters, deployment pipelines, observability, tenant isolation. That's nothing like building installable Windows software. And it's what I want to be doing next.

## What I'm Watching

How VDC evolves over the next year will be telling. Does it expand beyond M365 and Azure? AWS? Kubernetes workloads? The Cirrus acquisition that laid the groundwork was Azure-focused, but the architecture could extend to other clouds.

I also want to see how the partner relationship plays out. VCSPs are Veeam's bread and butter, and that balance needs to be handled carefully. Going to go read the partner FAQ before my inbox fills up on Monday.
