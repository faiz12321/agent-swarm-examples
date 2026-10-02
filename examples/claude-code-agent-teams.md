# Claude Code agent teams

**Evidence label:** Documented feature  
**By:** Anthropic  
**Date:** Docs read 2 October 2026 (v2.1.178)

**Agents:** Lead plus teammates  
**Reported cost:** Significantly more tokens than one session  
**Reported outcome:** Feature, no outcome claim

## Sources

- [Claude Code docs: Orchestrate teams of Claude Code sessions](https://code.claude.com/docs/en/agent-teams)

## What it is

A built-in way to run several Claude Code sessions as a team. One session is the lead, teammates work in their own context windows, share a task list and message each other directly.

## How the agents coordinate

Lead plus teammates, shared tasks, direct messaging between teammates (unlike subagents, which only report back).

## Setup

Experimental and off by default. Set CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS=1 in settings or the environment.

## Limits and caveats

- Docs say it adds coordination overhead and uses significantly more tokens, scaling with teammates.
- Docs recommend a single session or subagents for sequential tasks, same-file edits or many dependencies.
- Docs list known limitations, including tmux caveats outside macOS.

[Back to the index](../README.md)
