# Anthropic Research: lead agent with parallel subagents

**Evidence label:** Vendor-reported product or eval  
**By:** Anthropic engineering  
**Date:** 13 June 2025

**Agents:** Lead plus parallel subagents  
**Reported cost:** About 15x chat tokens  
**Reported outcome:** 90.2% better than single agent on internal eval

## Sources

- [Anthropic engineering: How we built our multi-agent research system](https://www.anthropic.com/engineering/multi-agent-research-system)

## What it is

The Research feature in Claude. A lead agent plans a research task and starts subagents that search in parallel, then synthesizes their findings. Anthropic reports that a Claude Opus 4 lead with Claude Sonnet 4 subagents beat single-agent Opus 4 by 90.2% on its internal research eval.

## How the agents coordinate

Orchestrator and workers. The lead saves its plan to memory, spawns subagents with their own context windows, and they return condensed results.

## Setup

Described in the post with prompting lessons. The product itself is not open source.

## Limits and caveats

- Internal eval, not independently checked.
- Anthropic says multi-agent systems use about 15 times more tokens than chat, so the task has to be worth it.
- Works best for broad, parallel questions. Anthropic calls it a multi-agent system, not a swarm.

[Back to the index](../README.md)
