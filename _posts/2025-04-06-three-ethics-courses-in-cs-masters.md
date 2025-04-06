---
title: "I Took Three Ethics Courses in My CS Master's. Here's Why."
date: 2025-04-06 18:45:00 -0400
categories: [Education, Computer Science]
tags: [ethics, ai, computer-science, graduate-school]
---

My MSCS transcript has three ethics courses on it:

- Computing, Ethics, and Society Foundations
- Ethical Issues in AI and Professional Ethics
- Ethical Issues in Computing Applications

When I tell other engineers this, I get a look. The "why would you waste elective slots on that" look. Fair question. Here's my answer.

## The Courses Aren't What You Think

I figured they.d be philosophy lectures. Instead they were case studies about real engineering failures: systems that shipped, caused harm, and could have been caught earlier if someone on the team had asked better questions.

Biased hiring algorithms that filtered out qualified candidates based on proxy variables for race. Recommendation systems that radicalized users by optimizing for engagement without guardrails. Facial recognition deployed in contexts where the error rate for certain demographics was orders of magnitude higher than others.

These weren't hypothetical scenarios. They were post-mortems of real products built by real engineers at companies you've heard of.

## What It Changed About How I Build Things

I work in cloud infrastructure now. I'm not building recommendation algorithms or facial recognition systems. But the core lesson applies everywhere: the systems we build have consequences beyond their intended use, and engineers are in the best position to identify those consequences early.

When I'm designing a platform feature, I now ask questions I wouldn't have asked before:

- **Who doesn't have access to this?** If I build a self-service portal that requires a VPN, I've excluded every contractor and remote partner. That's a design choice with consequences.
- **What happens when this fails?** Not just technically. Who gets paged, who loses productivity, whose deadline gets missed? Failure modes have human costs.
- **What data does this collect, and who can see it?** Even internal observability tools collect information about how individual developers work. That data can be used for performance reviews in ways you didn't intend.

None of these questions require an ethics degree. But having the formal framework helped me recognize patterns I was previously blind to.

## The AI Course Specifically

The generative AI and AI ethics courses hit different when you're watching the industry move as fast as it is right now. I took Introduction to Generative AI alongside the ethics courses, which meant I was simultaneously learning how these systems work and studying the ways they fail.

The takeaway that stuck with me: the engineers building AI systems are making ethical decisions whether they realize it or not. Every training dataset is a value judgment. Every prompt template is a design choice about who the system serves. "I just build the infrastructure" stops being a defensible position when the infrastructure enables harm at scale.

## Do I Recommend It?

If your program offers ethics courses, take at least one. Not because it looks good on a transcript. It doesn't move the needle on hiring. Take it because it makes you a better engineer. The technical courses teach you how to build things. The ethics courses teach you to ask whether you should, and for whom.
