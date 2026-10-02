# Anthropic: 16 Claude agents writing a C compiler

**Evidence label:** Builder-reported experiment  
**By:** Nicholas Carlini, Anthropic Safeguards team  
**Date:** 5 February 2026

**Agents:** 16  
**Reported cost:** About $20,000  
**Reported outcome:** 100,000-line compiler that Anthropic says builds Linux 6.9; known gaps

## Sources

- [Anthropic engineering: Building a C compiler with a team of parallel Claudes](https://www.anthropic.com/engineering/building-c-compiler)
- [Code: anthropics/claudes-c-compiler](https://github.com/anthropics/claudes-c-compiler)

## What it is

16 agents wrote a Rust C compiler from scratch. Across nearly 2,000 Claude Code sessions and about $20,000 in API cost, they produced a 100,000-line compiler that Anthropic says builds Linux 6.9 on x86, ARM and RISC-V.

## How the agents coordinate

No orchestrator. Each agent runs in its own Docker container in an endless loop, clones a shared git repo, takes a task by writing a lock file in current_tasks/, works, merges and pushes. Git stops two agents taking the same task. Some agents had fixed roles: merging duplicate code, speeding up the compiler, critiquing design.

## Setup

A bash loop calling Claude Code with a prompt file, one container per agent, a bare git repo. The author says most effort went into tests, because agents solve whatever the tests measure. For the Linux kernel, where all agents hit the same bug, he used GCC as a known-good oracle so agents could work on different files.

## Limits and caveats

- The author lists gaps: no own assembler and linker that work reliably, and a 16-bit x86 mode that Opus could not finish within size limits.
- New features often broke old ones.
- The repo README says not to use the code and that none of it is validated.

[Back to the index](../README.md)
