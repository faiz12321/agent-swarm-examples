# The Swarm Diaries: five agents, five branches, one crash

**Evidence label:** Independent practitioner report  
**By:** Microsoft Apps on Azure blog (author shown as larohra)  
**Date:** 18 March 2026

**Agents:** 5 as described, 6 in a test run  
**Reported cost:** Not stated  
**Reported outcome:** Quality score 28 to 68 after interface contracts

## Sources

- [Post: The Swarm Diaries](https://techcommunity.microsoft.com/blog/appsonazureblog/the-swarm-diaries-what-happens-when-you-let-ai-agents-loose-on-a-codebase/4501393)

## What it is

A build of a coding swarm on Azure Durable Task Scheduler. A deterministic workflow breaks a goal into a task graph, runs agents in parallel in separate Docker containers on separate git branches, merges and runs quality checks. The author hit failures: agents wrote incompatible modules (one used a JSON file store, the other SQLite), an agent got no tools because of a naming bug yet reported success, and an LLM was used for merges that plain git handled in seconds.

## How the agents coordinate

A fixed workflow (the brain) plus agents in containers (the hands). Agreed interface contracts between agents were the fix: in one test, quality score went from 28 to 68 and branch conflicts from three of six to zero of four.

## Setup

Azure Durable Task Scheduler, Microsoft Agent Framework, Docker. The post is a write-up; check it for a code link.

## Limits and caveats

- Written by a Microsoft author on a Microsoft blog about Microsoft tools.
- Main lesson in his words: verify what agents did, not what they said they did.

[Back to the index](../README.md)
