---
title: "VeeamON 2025: Entra ID Backup and the MCP Integration Nobody Expected"
date: 2025-04-27 17:00:00 -0400
categories: [Veeam, Cloud]
tags: [veeam, vdc, veeamon, entra-id, mcp, ai, cloud-infrastructure]
---

VeeamON 2025 just wrapped in San Diego. Two things stood out to me.

## Entra ID Backup

If you manage Azure infrastructure, you already know Entra ID is the thing holding everything together. Users, groups, roles, service principals, conditional access policies. It all lives there, and when someone breaks it, the blast radius is enormous.

I've watched partners accidentally delete a service principal and spend hours trying to figure out what it was even connected to. There was no undo button. You just had to reconstruct it from memory and hope you got the permissions right.

VDC now backs up full Entra ID tenants (users, groups, admin units, roles, applications, audit and sign-in logs) with granular restore. There's also a change detection feature that diffs your live tenant against a known-good backup. That's the part I'm most interested in. Instead of "something changed and nobody knows what," you can actually see what moved. I could've used that about fifty times in the last year alone.

## The MCP Thing

This one I genuinely didn't see coming. Veeam announced they're building integration with Anthropic's Model Context Protocol so AI systems can query data stored in backup repositories.

I'm still wrapping my head around what this means in practice. The basic idea is that backup data becomes something an AI agent can search through, instead of just sitting in cold storage waiting for someone to hit restore. So in theory you could ask "what changed in our Entra ID tenant last month" and get an answer without writing KQL or digging through logs manually.

Whether that actually works as smoothly as the demo suggested remains to be seen. I'm curious but skeptical. Vendor conferences are where demos always work perfectly. Interesting concept though. What if backup data is actually useful for something other than restores?

## What I'm Actually Thinking About

Zooming out, VDC has changed a lot in 18 months. It started as BaaS for M365 and Azure, then added Vault for storage, and now Entra ID backup and an AI integration layer. Whoever is building the platform infrastructure behind all of this is solving genuinely hard multi-tenant cloud problems, and those are the kinds of problems I want to be working on.

They also announced a CrowdStrike partnership for Falcon LogScale and Next-Gen SIEM integration. More APIs, more security overlap, more infrastructure complexity. The backup server keeps getting further from being just a backup server.
