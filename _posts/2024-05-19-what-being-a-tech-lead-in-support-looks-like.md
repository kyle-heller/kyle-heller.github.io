---
title: "What Being a Tech Lead in Support Actually Looks Like"
date: 2024-05-19 15:45:00 -0400
categories: [Career, Veeam]
tags: [veeam, tech-lead, leadership, mentoring, support-engineering]
---

When I got promoted to Technical Lead at Veeam, I expected it to feel like a bigger version of the same job. Harder cases, more responsibility, maybe some meetings. What I actually got was a completely different role that happened to share a building with my old one.

## You Stop Solving Problems and Start Teaching People to Solve Problems

The hardest adjustment was letting go of the keyboard. As a support engineer, my value was measured by how many cases I closed and how fast I resolved them. As a tech lead, my value is measured by how effectively my team resolves cases, which means the best use of my time is often *not* fixing the problem myself.

A junior engineer comes to me with a stuck replication job. I know the answer. It's a network MTU mismatch. I've seen it a hundred times. The temptation is enormous to just tell them the answer and move on. I have to physically stop myself sometimes. But if I do that, they learn nothing. Next time they see the same symptom, they'll come back to me.

Instead, I walk them through the diagnostic path. "What do the logs show? What layer does that error suggest? What would you check next?" It takes three times longer than just giving the answer. But after a few of these sessions, they stop coming to me for MTU mismatches. They start recognizing the pattern themselves.

That's the job. It's not glamorous. It doesn't look impressive on a metrics dashboard. But it's how you scale a team's capability beyond what any one person can do alone.

## Playbooks Are How You Scale Yourself

Early on I realized I was answering the same questions repeatedly. Different engineer, different customer, same root cause pattern. So I started writing playbooks.

Not the kind of documentation that gets written once, filed in Confluence, and slowly decomposes. You know the kind I mean. Actual decision-tree playbooks: "If you see X in the logs, check Y. If Y looks normal, check Z." Structured, specific, and written in the language engineers actually use during troubleshooting.

As a KCS Knowledge Domain Expert, I had the framework to do this properly. But the real driver wasn't process. It was the realization that my knowledge was a bottleneck. If the team could only solve complex problems when I was available, we had a single point of failure. The playbooks distribute that knowledge.

## The Liaison Work Nobody Tells You About

A significant chunk of my time goes to cross-functional communication. When a partner's production environment reveals a product bug, I'm the one translating between support (who sees the customer impact), R&D (who needs reproducible evidence), and QA (who needs test cases).

Each of those teams speaks a different language and has different priorities. Support wants a workaround now. R&D wants a root cause analysis with logs and a reproducible test case. QA wants to know the scope of impact and regression risk.

My job is to give each team what they need in the format they need it. That means writing one report that's simultaneously a customer-facing workaround, a developer-facing bug report, and a QA-facing test plan. It's technical writing, relationship management, and priority negotiation all at once.

Nobody warned me this would be the biggest part of the job. It is.

## Would I Do It Again?

Yes. The tech lead role taught me things about leadership, communication, and organizational dynamics that no engineering course covers. It also showed me that I want to build things, not just fix them, which is why I'm interested in moving toward more engineering-focused roles. But the leadership skills transfer directly. Engineering is still about making other people more effective. The tools are different. The goal is the same.
