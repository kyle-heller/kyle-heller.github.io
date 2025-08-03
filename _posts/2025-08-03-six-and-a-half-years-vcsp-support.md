---
title: "Six and a Half Years of Cloud Service Provider Support: What It Teaches You About Production Infrastructure"
date: 2025-08-03 14:00:00 -0400
categories: [Career, Veeam]
tags: [veeam, vcsp, support-engineering, cloud-infrastructure, career]
---

I've been at Veeam for six and a half years. I started as a support engineer taking calls from cloud service provider partners, and I'm now a Technical Lead running architectural assessments on their production environments. Along the way, I've seen more infrastructure failures than most engineers see in a career. When you're in VCSP support, that's just the job. A firehose of real-world production problems from dozens of different environments every week.


## The environments

In theory, our partners follow reference architectures. In practice, every partner's environment is a unique combination of hypervisor, storage, and network decisions nobody documented that produced something no architecture diagram predicted.

When you troubleshoot hundreds of these environments, you stop assuming anything about how infrastructure is configured. You learn to verify everything. "What version are you running?" "What's behind the load balancer?" "Is that storage backed by SAN or local disk?" These questions become reflexive because you've been burned too many times by assumptions.

Verify, don't assume. That's probably the most useful thing I got from support.

## Unexpected failures

Documentation covers expected failure modes. Production generates unexpected ones. I've seen:

- Backup jobs failing because a storage array firmware update changed the behavior of a SCSI command that had worked the same way for a decade
- Replication breaking because a partner's ISP started doing transparent proxy injection on specific TCP ports
- An entire Cloud Connect environment going down because a certificate renewal script ran during peak backup window and briefly interrupted TLS connections to every tenant

None of these are in any troubleshooting guide. You diagnose them by understanding the full stack: application, OS, network, storage, and the interactions between them. Being able to think across all those layers at once is what you get from years of support.

## Outages

When a partner calls in and their production backup environment is down, they're not having a technical problem. They're having a business problem. Their customers are unprotected. Their SLAs are being violated. Their phone is ringing with calls from people who are angry and scared.

You have to diagnose the issue while also keeping the customer calm, giving them honest updates, and not making promises you can't keep. Doing all of that at once is a skill. Nobody tests you on it, but it might be the most important one.

It also changes how you design systems later. When you've been the person on the phone during an outage, you think differently about alerting, about runbooks, about mean time to recovery. You stop designing for best-case scenarios. You start designing for the worst call you've ever taken.

## Why I'm Still Here

Seven years at one company is unusual in tech. People ask why I haven't jumped. The honest answer is that I kept getting different jobs without changing companies. I went from answering phones to leading a team of engineers to doing architectural reviews of production cloud environments. Each step built on the last one because I had the institutional knowledge and the relationships to make it happen.

The VCSP ecosystem specifically is a unique environment. You're not just learning one company's infrastructure. You're learning how hundreds of companies build and operate their cloud platforms. Every partner engagement is a case study in how real organizations make infrastructure decisions, and how those decisions play out over time.

I've thought about whether a bigger title somewhere else would be worth giving that up. The math doesn't work for me.

## What's Next

I'm increasingly interested in building infrastructure rather than just supporting it. I don't think the support years were a detour though. It's hard to build resilient systems if you've never watched things fall apart up close.
