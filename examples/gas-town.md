# Gas Town

**Evidence label:** Open-source project  
**By:** Steve Yegge  
**Date:** Open-sourced 1 January 2026

**Agents:** Aims at 20 to 30  
**Reported cost:** Not stated in README  
**Reported outcome:** Open-source orchestrator

## Sources

- [Code: gastownhall/gastown (MIT)](https://github.com/gastownhall/gastown)
- [Essay: Welcome to Gas Town](https://yegge.ai/essays/welcome-to-gas-town/)
- [Later post: Gas Town, from Clown Show to v1.0](https://steve-yegge.medium.com/gas-town-from-clown-show-to-v1-0-c239d9a407ec)
- [DoltHub field reports (see next entry)](https://www.dolthub.com/blog/2026-01-15-a-day-in-gas-town/)

## What it is

An orchestrator for running 20 to 30 Claude Code instances at once, which the README says replaces the chaos that starts around 4 to 10 unmanaged agents.

## How the agents coordinate

A Mayor agent you talk to, ephemeral worker agents called polecats that each work in their own git worktree, watchdog agents (Witness, Deacon), a merge queue (Refinery), convoys that group related work, and Beads, a git-backed issue tracker that holds work state outside agent memory.

## Setup

Claude Code or other agents, git, tmux and the Beads tool. The README is the source for exact install steps.

## Limits and caveats

- Yegge warned people not to use it in its first weeks, according to Lakshmi Narasimhan's report.
- Fast moving: Yegge has since posted about a v1.0 and a follow-on called Gas City. Check the repo for current state.
- Costs and failures reported by users are in the two field-report entries.

[Back to the index](../README.md)
