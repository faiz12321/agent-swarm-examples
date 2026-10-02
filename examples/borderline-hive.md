# Hive: issue-to-pull-request agent pipeline

**Evidence label:** Borderline  
**By:** Nick Jensen  
**Date:** 31 January 2026

**Agents:** One per repo at a time  
**Reported cost:** Not stated  
**Reported outcome:** Author estimates 60% of straightforward work

## Sources

- [Post: I Built an Autonomous Coding Swarm. Here's What I Learned.](https://www.nickjensen.co/posts/autonomous-coding-swarm-lessons)

## What it is

A system that turns Linear issues into pull requests with Claude Code, with a queue, a runner and per-repo context files. The author says it covers about 60% of straightforward implementation work and he reviews each pull request.

## How the agents coordinate

A queue that allows one agent per repo at a time. So agents do not run in parallel on the same codebase, which is why this is borderline despite the word swarm in the title.

## Setup

Linear webhooks, an orchestrator, a queue and a runner that starts Claude Code.

## Limits and caveats

- Read for its design only. The 60% figure is the author's own estimate.

[Back to the index](../README.md)
