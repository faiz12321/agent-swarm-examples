# Cursor: a swarm of hundreds of agents building a web browser

**Evidence label:** Builder-reported experiment  
**By:** Wilson Lin, Cursor  
**Date:** 14 January 2026

**Agents:** Hundreds, concurrent  
**Reported cost:** Trillions of tokens, no dollar figure  
**Reported outcome:** Browser proof of concept; Cursor says far from polished

## Sources

- [Cursor blog: Scaling long-running autonomous coding](https://cursor.com/blog/scaling-agents)

## What it is

Cursor ran hundreds of agents at once on a single project, a web browser written from scratch. They report the agents ran for close to a week and wrote over 1 million lines of code across 1,000 files. Other runs they list: a Solid to React migration in their own codebase (over three weeks, +266K/-193K edits, passing CI but still needing careful review), and a Rust rewrite of video rendering they say is 25x faster and was merged.

## How the agents coordinate

First try: equal agents sharing a task file with locks. Twenty agents slowed to the speed of two or three, and agents avoided hard tasks. Second try, which they kept: planners that explore the code and create tasks (and can spawn sub-planners), workers that only do their task and push, and a judge agent that decides whether to start another cycle.

## Setup

Not published as a recipe. Cursor says the prompts mattered more than the harness. It picked models per role: it found GPT-5.2 better than Opus 4.5 for extended autonomous work, and better than GPT-5.1-Codex as a planner.

## Limits and caveats

- Cursor's own later post says the browser swarm 'succeeded as a proof of concept, but fell far short of polished software'.
- Cost is trillions of tokens, no dollar figure given.
- Agents sometimes run far too long and need periodic fresh starts.

[Back to the index](../README.md)
