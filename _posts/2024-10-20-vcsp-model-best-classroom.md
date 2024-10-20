---
title: "Why the Cloud Service Provider Model Is the Best Classroom in Infrastructure"
date: 2024-10-20 14:15:00 -0400
categories: [Career, Veeam]
tags: [veeam, vcsp, cloud-infrastructure, multi-tenancy, career]
---

Most engineers work on one infrastructure environment. Maybe two if they're lucky and have a decent home lab. I've worked on hundreds, and I didn't have to change jobs to do it.

Veeam's Cloud and Service Provider (VCSP) program partners with managed service providers and hosting companies who build backup-as-a-service and disaster-recovery-as-a-service platforms on top of Veeam products. My team supports those partners. That means every week I'm looking at a different company's production infrastructure.

## The Variety Is the Education

One partner runs everything on VMware with NetApp storage behind a Cisco network. The next runs Hyper-V on Dell PowerStore with a Juniper fabric. A third is all-in on Azure with AKS and managed disks. Each one made different architectural decisions for different business reasons, and each one generates different failure modes.

After a few hundred of these engagements, you develop pattern recognition that crosses vendor boundaries. You stop thinking in terms of specific products and start thinking in terms of infrastructure primitives: compute, storage, networking, identity, and the interactions between them. That abstraction layer is exactly what cloud engineering requires.

## Multi-Tenancy Is Not Optional

VCSP partners are multi-tenant by definition. They host multiple customers on shared infrastructure with isolation requirements, different SLAs, and different retention policies. The infrastructure has to handle tenant onboarding, resource isolation, certificate management, and noisy-neighbor problems at scale.

Supporting these environments taught me more about multi-tenancy than any architecture course. When a partner asks "why is Tenant A's backup job slow?" and the answer is "because Tenant B is running a restore that's saturating the storage controller," you learn real fast why resource quotas and QoS policies exist. Nothing teaches you multi-tenancy like an angry call from Tenant A because Tenant B is hogging the storage controller.

That multi-tenant mindset transfers directly to cloud infrastructure roles, where internal developer teams are essentially tenants on a shared platform with competing resource needs.

## Production Data Protection Raises the Stakes

Here's what makes Veeam's space different from a lot of infrastructure work: you're protecting production data. When a backup fails, that customer's data is unprotected. When a disaster recovery failover doesn't work, someone's business continuity plan just evaporated.

That severity level shapes how you think about reliability. You don't get to say "we'll fix it in the next sprint." The data is either protected or it isn't. There's no partial credit.

Working in that environment for almost six years gave me a deep appreciation for what "production-grade" actually means. It's not a marketing term. It's the difference between a system that works in a demo and a system that works at 2 AM on a Saturday when everything else is on fire.

## The Underrated Perk

The VCSP ecosystem is also a network of hundreds of infrastructure professionals: the engineers at partner companies who build and operate these environments daily. I've built relationships with people running production platforms at companies across North America. That network has taught me as much as any formal education, and it's the kind of professional community that takes years to build.
