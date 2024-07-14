---
title: "How I Automated Myself Out of Hours of Weekly Reporting at Veeam"
date: 2024-07-14 19:30:00 -0400
categories: [Automation, Veeam]
tags: [automation, veeam, n8n, puppeteer, python, productivity]
---

Every week, I was spending hours on compliance reporting. Pull data from one system, cross-reference it with another, format it for leadership, paste it into the right template. It was the kind of work that felt productive because it was time-consuming. It wasn't productive. It was just slow.

I'm a Technical Lead on the NA VCSP Support team at Veeam. My job is supposed to be leading architectural assessments, mentoring engineers, and driving resolution on critical production issues. Not copying data between browser tabs.

So I automated it.

## The Stack

Nothing exotic. n8n for workflow orchestration, Puppeteer for browser automation (some of our data sources don't have APIs), and Python for data transformation and formatting. The whole thing runs on a schedule and drops a finished report where it needs to go.

## Why n8n

I looked at a few options. Could have written a pure Python script. Could have used Power Automate since we're a Microsoft shop. I chose n8n because it gave me a visual workflow builder that I could hand off to someone else if needed, while still letting me drop into code nodes when the logic got complex.

The visual aspect matters more than engineers usually admit. When I'm debugging a workflow that pulls from three data sources, transforms the output, and pushes it somewhere else, being able to *see* the pipeline as a diagram is faster than reading through 200 lines of procedural code.

## The Puppeteer Part

This is the part that feels hacky, and I won't pretend otherwise. Some of the systems I needed to pull data from are internal web tools with no API. The only way to get the data out was to literally automate a browser session: log in, navigate to the right page, scrape the table, parse the HTML.

Is that fragile? Extremely yes. If someone changes the UI, the scraper breaks. But the alternative was me doing it by hand every week. A scraper that breaks once a quarter and takes 20 minutes to fix is still better than a human doing 3 hours of manual work 52 times a year.

## The Result

Weekly reporting that took 2-3 hours now takes zero. The automation runs, the report lands, I review it for sanity in about 5 minutes. That's roughly 130 hours a year I got back, hours I now spend on actual engineering work.

More importantly, the reports are more accurate. Manual data entry introduces errors. Copy-paste introduces errors. Humans reading numbers off one screen and typing them into another screen introduce errors. The automation doesn't.

I keep looking for the next thing to automate. My wife says I have a problem. She's probably right. Once you get those hours back, you start noticing all the other places you're being a human ETL pipeline.
