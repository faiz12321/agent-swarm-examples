# Kimi Agent Swarm

**Evidence label:** Vendor-reported product or eval  
**By:** Moonshot AI (Kimi)  
**Date:** Released 27 January 2026 with Kimi K2.5

**Agents:** Up to 100 (blog) or 300 (help centre)  
**Reported cost:** Not stated  
**Reported outcome:** 4.5x faster than sequential (Kimi's claim)

## Sources

- [Kimi blog: Agent Swarm](https://www.kimi.ai/blog/agent-swarm)
- [Kimi help centre: Agent Swarm](https://www.kimi.ai/help/agent/agent-swarm)
- [Kimi K2.5 technical report (arXiv)](https://arxiv.org/html/2602.02276)

## What it is

A product feature where one orchestrator creates sub-agents on its own and runs them in parallel, for tasks like researching many items at once. Kimi's launch blog claims up to 100 sub-agents, over 1,500 tool calls and results 4.5x faster than sequential execution.

## How the agents coordinate

A self-organizing orchestrator that decides roles and spawns agents, with no hand-written roles or workflow. Kimi's help centre describes it as scale-out, up to 300 sub-agents.

## Setup

Used through Kimi. The K2.5 model is described as open source in the technical report.

## Limits and caveats

- The two Kimi pages give different maximums (100 on the blog, 300 in the help centre).
- Speed and quality figures are Kimi's own claims. Not independently checked here.

[Back to the index](../README.md)
