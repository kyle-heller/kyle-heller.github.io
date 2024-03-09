---
title: "Veeam Data Cloud Just Launched and I Have Thoughts"
date: 2024-03-08 21:00:00 -0500
categories: [Veeam, Cloud]
tags: [veeam, vdc, veeam-data-cloud, azure, baas, cloud-infrastructure]
---

Veeam just announced Veeam Data Cloud, a fully managed BaaS offering built on Azure for Microsoft 365 and Azure workloads. As someone who's spent five years supporting VCSP partners who deliver exactly this kind of service, this announcement landed differently for me than it might for most people.

## What VDC Is

Veeam Data Cloud is Veeam's first real SaaS play. Instead of selling software that partners or customers install, manage, and operate, Veeam is now selling the outcome directly: backup and recovery as a service. Software, infrastructure, storage: all bundled, all managed by Veeam, all running on Azure.

For Microsoft 365, it's built on the same Veeam Backup for Microsoft 365 engine that already protects 18 million users. For Azure, it covers VMs, Azure SQL, and Azure Files. Zero Trust architecture, immutable storage, the works.

## Why It's Interesting to Me Specifically

I support cloud service providers for a living. These partners have built entire businesses around hosting Veeam infrastructure and selling backup services to their customers. VDC is, in some ways, Veeam competing with its own partner ecosystem.

That's not necessarily a bad thing. The market is segmenting. Large enterprises increasingly want first-party BaaS from the vendor itself. The 2024 Data Protection Trends Report showed 88% of organizations intend to use BaaS or DRaaS within two years. Partners who add value through managed services, customization, and multi-vendor support will continue to thrive. Partners who were essentially reselling Veeam with minimal value-add have a harder road.

But the more interesting thing to me is what VDC represents *technically*. Veeam is now operating a large-scale, multi-tenant SaaS platform on Azure. That means someone inside Veeam is building and running the platform infrastructure: the Kubernetes clusters, the deployment pipelines, the observability stack, the tenant isolation, the autoscaling. That's a massive engineering effort.

## The Platform Behind the Product

Think about what VDC requires under the hood. You need automated tenant provisioning. You need isolated backup storage per customer with immutability guarantees. You need a control plane that manages backup policies across thousands of tenants. You need CI/CD pipelines that deploy updates without downtime. You need monitoring that catches problems before customers notice them.

That's cloud-native infrastructure engineering, not backup engineering. And it's happening inside Veeam right now.

As someone who's spent years on the support side watching Veeam evolve, VDC is the most exciting thing the company has done in years. Not just because of what it does for customers (though that's great), but because of what it signals about where the company is heading technically. Veeam is becoming a cloud platform company, and that requires a fundamentally different engineering culture than building installable Windows software.

## What I'm Watching

How VDC evolves over the next year will tell us a lot. Will it expand beyond M365 and Azure? Will there be a Veeam Data Cloud for AWS? For Kubernetes workloads? The Cirrus acquisition that laid the groundwork was Azure-focused, but the architecture could theoretically extend to other clouds.

I'm also watching the partner ecosystem reaction. VCSP partners are Veeam's bread and butter, and the relationship between first-party BaaS and partner-delivered BaaS needs to be handled carefully. My partners are already asking questions.

Interesting times at Veeam. I need to go read the partner FAQ before my inbox fills up.
