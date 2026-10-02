# Cursor: planner and worker swarm rebuilding SQLite

**Evidence label:** Builder-reported experiment  
**By:** Wilson Lin, Cursor  
**Date:** 20 July 2026

**Agents:** Not stated  
**Reported cost:** Varies by model mix; chart only  
**Reported outcome:** 80% of a held-out SQL suite in 4 hours (Grok 4.5, new design)

## Sources

- [Cursor blog: Agent swarms and the new model economics](https://cursor.com/blog/agent-swarm-model-economics)

## What it is

Cursor asked a swarm to build SQLite in Rust from its documentation alone, and scored it on a held-out SQL test suite. They report the new swarm design beat the old one in every model setup. With Grok 4.5 it reached 80% in four hours, while the old swarm spiraled and was paused before its second hour. Mixing a frontier planner with cheaper workers gave similar quality at very different cost.

## How the agents coordinate

A tree. Planner agents (smarter models) split a goal and delegate. Worker agents (faster, cheaper models) do the pieces. Planners never implement and workers never plan, which Cursor thinks is why it scales: context stays small. They also built a version control layer for agents, saying their peak went from about 1,000 commits per hour to about 1,000 per second.

## Setup

Internal tooling. No public code in the post.

## Limits and caveats

- Results are Cursor's own, on one task.
- Cursor says the browser swarm was a first, empirical design and this is a rework.

[Back to the index](../README.md)
