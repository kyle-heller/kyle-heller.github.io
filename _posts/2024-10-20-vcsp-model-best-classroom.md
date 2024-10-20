---
title: "Why the Cloud Service Provider Model Is the Best Classroom in Infrastructure"
date: 2024-10-20 14:15:00 -0400
categories: [Career, Veeam]
tags: [veeam, vcsp, cloud-infrastructure, multi-tenancy, career]
---

Most engineers work on one infrastructure environment. Maybe two if they're lucky and have a decent home lab. I've worked on hundreds, and I didn't have to change jobs to do it.

Veeam's Cloud and Service Provider (VCSP) program partners with managed service providers and hosting companies who build backup-as-a-service and disaster-recovery-as-a-service platforms on top of Veeam products. My team supports those partners. That means every week I'm looking at a different company's production infrastructure.

## The Variety Is the Education

One partner runs everything on VMware with NetApp storage behind a Cisco network. The next is Hyper-V on Dell PowerStore with Juniper switches. Another went all-in on Azure. They all made different decisions for different business reasons, and they all break in different ways.

After a few hundred of these engagements, you start seeing past the vendor labels. You stop thinking "this is a NetApp problem" or "this is a VMware problem" and start thinking "this is a storage latency problem" or "this is a network segmentation problem." That's the shift. And it's exactly how you need to think for cloud work.

## Multi-tenancy

VCSP partners are multi-tenant by definition. They host multiple customers on shared infrastructure with different SLAs and retention policies. The infrastructure has to handle tenant onboarding, resource isolation, certificate management, and noisy-neighbor problems.

Supporting these environments taught me more about multi-tenancy than any architecture course. When a partner asks "why is Tenant A's backup job slow?" and the answer is "because Tenant B is running a restore that's saturating the storage controller," you learn real fast why resource quotas and QoS policies exist. Nothing teaches you multi-tenancy like an angry call from Tenant A because Tenant B is hogging the storage controller.

That multi-tenant mindset transfers directly to cloud infrastructure roles, where internal developer teams are essentially tenants on a shared platform with competing resource needs.

## Production stakes

The thing that makes Veeam's space different from a lot of infrastructure work: you're protecting production data. When a backup fails, that customer's data is unprotected. When a disaster recovery failover doesn't work, someone's business continuity plan just evaporated.

That severity level shapes how you think about reliability. You don't get to say "we'll fix it in the next sprint." The data is either protected or it isn't. There's no partial credit.

Six years of that taught me what "production-grade" actually means. It's not a buzzword. It means the thing still works when it's Saturday night and three other things are broken.

## The network

The VCSP ecosystem is also hundreds of infrastructure professionals, the engineers at partner companies who build and operate these environments daily. I've built relationships with people running production platforms at companies across North America. I've learned as much from those conversations as from any course, and they took years to build.
