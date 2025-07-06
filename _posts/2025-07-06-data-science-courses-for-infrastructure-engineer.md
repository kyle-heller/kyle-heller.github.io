---
title: "Why I Took Data Science Courses as an Infrastructure Engineer"
date: 2025-07-06 15:00:00 -0400
categories: [Education, Data Science]
tags: [data-science, slo, infrastructure, graduate-school, statistics]
---

My MSCS at CU Boulder included a graduate certificate in Data Science. Probability theory, statistical inference, regression and classification, data mining methods and pipeline. On paper, that has nothing to do with my actual job.

In practice, it shows up more than you'd think.

## SLOs Are Just Statistics

The first time I tried to set an SLO for platform availability, I realized I didn't actually understand what "99.9% available" meant in statistical terms. How many data points do you need before that number is meaningful? What's the confidence interval? If you measured 99.95% over 7 days, is that statistically different from 99.9%?

These aren't academic questions. They determine whether you alert your on-call engineer at 3 AM or not. They determine whether you tell leadership the platform is meeting its targets or missing them. Get the statistics wrong and you're either waking people up for nothing or sleeping through real incidents.

The probability and inference courses gave me the vocabulary and the math to think about reliability metrics properly. When I set an error budget now, I can explain *why* the window is 30 days and not 7, and *why* the burn rate threshold is where it is.

## Log Analysis Is Data Mining

When you're trying to figure out why deploy times spiked last Tuesday, you're doing data mining. When you're looking at resource utilization patterns across 12 clusters to figure out which ones need more capacity, you're doing regression. When you're categorizing incidents by root cause to prioritize platform improvements, you're doing classification.

I was doing all of these things before the coursework. But I was doing them with gut instinct and spreadsheet pivots. After the data mining courses, I had actual methods: clustering for pattern detection, decision trees for categorization, pipeline design for repeatable analysis.

## The Project That Connected It

One of my graduate projects involved building a classification pipeline for detecting PII in text data. That specific use case isn't relevant to my day job. But the *process*, acquiring data, cleaning it, selecting features, training a model, evaluating results, iterating, is the same process you use for any data-driven decision.

The data mining project course forced me to take a problem end-to-end. Not just "here's a clean dataset, run a model." Real data. Messy data. Data that required judgment calls about what to keep and what to throw away. That's closer to what production observability data looks like than any textbook example.

## Am I a Data Scientist?

No. I'm an infrastructure engineer who can read a paper, understand a statistical claim, and apply basic analytical methods to infrastructure problems. That's a different thing, and it's enough. I don't need to build neural networks. I just need to know when an alert threshold actually means something and when it's noise. That's all.

If your MSCS program offers data science electives, they're worth considering even if you're on the infrastructure track. The overlap isn't obvious until you're knee-deep in SLO dashboards wondering if your numbers actually mean anything.
