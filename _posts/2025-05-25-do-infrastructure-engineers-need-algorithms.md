---
title: "Do Infrastructure Engineers Need Algorithms? Reluctantly, Yes."
date: 2025-05-25 13:15:00 -0400
categories: [Education, Computer Science]
tags: [algorithms, computer-science, infrastructure, career]
---

I took four algorithms-adjacent courses in my MSCS: Algorithms for Searching, Sorting, and Indexing; Dynamic Programming and Greedy Algorithms; Trees and Graphs; and the Georgia Tech Data Structures course. Going in, I figured these were the "eat your vegetables" courses. Required for the degree, probably useless for someone who provisions cloud infrastructure for a living. "When am I ever going to use this" energy.

Half true, it turns out.

## What I'll Never Use

I will never implement a red-black tree in production. I will never hand-write a merge sort. I will never need to prove that a graph traversal runs in O(V + E) at my day job. If you're evaluating these courses purely on "will I code this at work," the answer is mostly no.

## What I Use Constantly

Infrastructure is a graph. Services depend on other services. Network routes form paths. Terraform resources have dependency chains. Once you internalize how graph traversal works — BFS, DFS, topological sort — you start seeing infrastructure problems as graph problems. "Why is this deploy taking so long?" is often answered by "because the dependency graph has a critical path through these six resources that can't be parallelized." I wouldn't frame it that way without the coursework.

I also developed an intuitive sense for time complexity. I don't calculate Big-O at work. But I understand *why* a nested loop over 10,000 resources is going to be slow, and I can estimate roughly how slow. When I'm writing a Python script that processes log entries, I know the difference between an approach that scales and one that falls over at 100k entries. That intuition comes from the formal training even though I never write proofs anymore.

Dynamic programming was the weird one. DP taught me to think about overlapping subproblems and caching results. That's literally what memoization is, and memoization shows up everywhere in infrastructure: caching DNS lookups, caching Terraform plan results, caching container image layers. The concept transferred even though the implementation looks nothing like a textbook DP problem.

## The Interview Tax

Let's be honest about the other reason these courses matter: interviews. FAANG-tier companies will ask you to solve algorithm problems on a whiteboard or in a shared editor. You cannot pass those interviews without this knowledge. Whether that's a good hiring practice is a separate debate. The reality is that if your career plan includes a Tier 1 company at any point, you need algorithms.

I'd rather have learned them in a graduate program with grades and deadlines holding me accountable than trying to grind LeetCode on my own. The structured courses forced me to understand the *why* behind each algorithm, not just memorize the pattern.

## The Honest Take

If you're an infrastructure engineer and you'll never interview at a company that asks algorithm questions, you can probably skip the formal coursework. Read about graph algorithms and time complexity informally and you'll get 80% of the practical value.

But if there's any chance you'll want that Tier 1 job someday, take the courses now while you have the structure and motivation. Future you will be grateful when you're not panic-studying dynamic programming the night before an interview.
