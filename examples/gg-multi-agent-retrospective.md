# Eight layers of multi-agent setup, and why most were dropped

**Evidence label:** Independent practitioner report  
**By:** GG (itsgg.com)  
**Date:** Written 8 January 2026, rewritten September 2026

**Agents:** Several  
**Reported cost:** Cost rose with each agent  
**Reported outcome:** Went back to one agent per pull request

## Sources

- [Post: What I Built for Multi-Agent Coding, and What Survived](https://itsgg.com/blog/2026/01/08/multi-agent-development-workflow/)

## What it is

The author ran several coding agents in one repo with eight layers of coordination: shared rules file, git-based issue tracking, database locks, worktrees, validation skills, a learning corpus, git hooks, session protocols. By May he was running one agent per pull request. Worktrees, hooks and session protocols stayed.

## How the agents coordinate

Atomic task claims with locks and worktrees per task, before the author dropped the multi-agent part.

## Setup

Described layer by layer in the post.

## Limits and caveats

- His reasons: he could not explain the merged code, cost rose with every parallel agent, and checks belong in hooks rather than prompts.
- A useful counterexample that someone stopped using a swarm.

[Back to the index](../README.md)
