# Claude Code: subagents, agent view, agent teams and workflows compared

**Evidence label:** Documented feature  
**By:** Anthropic  
**Date:** Docs read 2 October 2026

**Agents:** Varies by approach  
**Reported cost:** Multiplies token use  
**Reported outcome:** Decision guide, no outcome claim

## Sources

- [Claude Code docs: Run agents in parallel](https://code.claude.com/docs/en/agents)

## What it is

Anthropic's own guide to four ways of running work in parallel in Claude Code, and when each fits. Only agent teams are described as a coordinated group where teammates message each other.

## How the agents coordinate

Subagents report back to the session that started them. Agent view sessions report only to you. Agent teams share a task list and message each other under a lead. Dynamic workflows use a script that runs many subagents and cross-checks results.

## Setup

Docs say agent teams do not isolate teammates in worktrees, so split the work so each teammate owns different files. Worktrees keep parallel sessions from editing the same files.

## Limits and caveats

- Running several sessions or subagents at once multiplies token usage, per the docs.
- Workers are Claude sessions only. Other tools need to be exposed as an MCP server.
- Documentation, not a field result.

[Back to the index](../README.md)
