# Anthropic: coordinating swarms for vulnerability finding and game building

**Evidence label:** Vendor-reported product or eval  
**By:** Anthropic research team  
**Date:** 13 August 2026

**Agents:** 45 (game: 10 to 80)  
**Reported cost:** 27M tokens for 266 findings vs 6.5M for 21  
**Reported outcome:** Many vulnerabilities found; game output poor

## Sources

- [Anthropic research: Patterns and problems in emerging multiagent systems](https://www.anthropic.com/research/multiagent-systems)

## What it is

Two experiments. In the first, 45 agents each got a virtual machine, a shared forum and the same prompt to find vulnerabilities in 15 open-source projects. For Claude Mythos Preview, the coordinating swarm found 266 vulnerabilities over a 27 million token run, against 21 over 6.5 million tokens for independent parallel agents. Only 12 were found by both. In the second, swarms built a web-playable fantasy game.

## How the agents coordinate

Peer agents with a shared forum, peer review of findings, and for the game a self-hosted repository and pull requests. No fixed boss.

## Setup

Not published.

## Limits and caveats

- Anthropic says the game end product was consistently poor.
- As agent count rose from 10 to 80, the share of merged pull requests fell steeply for some older models.
- The swarm used about four times the tokens, so the comparison is not per token.
- They say true multiagent systems are still in their infancy.

[Back to the index](../README.md)
