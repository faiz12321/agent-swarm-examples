# Eight coding agents on a game: split by area worked, split by task did not

**Evidence label:** Independent practitioner report  
**By:** Anthony DiPerna  
**Date:** 13 February 2026

**Agents:** 8  
**Reported cost:** Not stated  
**Reported outcome:** Per-level split worked; per-task split broke the build

## Sources

- [Post: When AI Multiplies Velocity and Chaos](https://anthonydiperna.com/2026/02/13/when-ai-multiplies-velocity-and-chaos/)

## What it is

He ran one Claude Code agent per game level, each limited to its own directory. That worked well. After a restart he regrouped as eight agents by task type (UI, controls, tutorial, bugs and so on) editing overlapping files. Commits grew large and a one-line null check ended up breaking level loading, which was hard to trace.

## How the agents coordinate

None beyond directory boundaries he enforced by prompt. He directed each agent by hand.

## Setup

Several Claude Code sessions on one repo.

## Limits and caveats

- One small hobby project.
- The lesson is about clear file boundaries, not about swarm performance.

[Back to the index](../README.md)
