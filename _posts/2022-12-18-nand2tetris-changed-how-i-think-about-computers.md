---
title: "Nand2Tetris Changed How I Think About Computers"
date: 2022-12-18 14:20:00 -0500
categories: [Education, Computer Science]
tags: [nand2tetris, computer-science, self-study, fundamentals]
---

If you work in tech and you've never taken Nand2Tetris, stop reading this and go do it. Seriously. It's free. It's the single most valuable self-study course I've ever completed.

## What It Is

The full name is "From Nand to Tetris: Building a Modern Computer from First Principles." You start with a single logic gate, a NAND gate, and by the end of the course you've built an entire computer. Hardware, CPU, assembler, virtual machine, compiler, operating system, and a working game running on top of it all. From nothing.

## Why It Matters for Infrastructure Engineers

I took this course while I was working in cloud infrastructure support. Every day I was troubleshooting compute, storage, and networking problems at an abstraction layer so high that the actual hardware was invisible. VMs, containers, APIs: everything was a black box.

Nand2Tetris cracked those boxes open.

After building an ALU from logic gates, I understood *why* bitwise operations work the way they do. After building a memory system from flip-flops, I understood *why* RAM is volatile and storage isn't. After writing an assembler, I understood *why* compiled code is faster than interpreted code. Not as a fact I memorized, but as something I experienced by building both.

None of this shows up on my resume. Nobody has ever asked me about logic gates in a job interview. But it fundamentally changed how I reason about every layer of the stack above it. When I'm debugging a container networking issue, I have a mental model that goes all the way down. That model came from this course.

## The Hard Part

It's not the content. It's the time. Each project took me 8-15 hours. I was doing this on weekends while working full-time. Some weekends I absolutely did not want to open the HDL simulator. Especially the CPU project — that one took me an entire Saturday and most of a Sunday. I did it anyway because each project built on the last one, and quitting at chapter 6 meant chapters 1-5 were wasted.

The course is designed so that each layer of the computer you build becomes the foundation for the next. There's no skipping ahead. That structure is what makes it effective and also what makes it demanding.

## Should You Do It?

If you work anywhere in the infrastructure or platform space, yes. You don't need a CS degree to do it. I certainly didn't have one when I started. You need patience, a few free weekends, and the willingness to be confused for a while before things click.

The clicks are worth it. Trust me on this one.
