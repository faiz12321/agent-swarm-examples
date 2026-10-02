# Three DoltHub reports on running Gas Town: costs, output and a leaked-token incident

**Evidence label:** Independent practitioner report  
**By:** Tim Sehn, DoltHub  
**Date:** 15 January, 24 March and 16 April 2026

**Agents:** Several (not counted)  
**Reported cost:** $100 per hour, $3,000 per week, about $6,000 per two weeks  
**Reported outcome:** Working DoltLite and DumboDB, code not trusted

## Sources

- [A Day in Gas Town](https://www.dolthub.com/blog/2026-01-15-a-day-in-gas-town/)
- [A Week In Gas Town](https://www.dolthub.com/blog/2026-03-24-a-week-in-gas-town/)
- [Two Weeks in Gas Town](https://www.dolthub.com/blog/2026-04-16-two-weeks-in-gastown/)

## What it is

The CEO of DoltHub, whose database Dolt is used by Gas Town, tried it three times. One hour cost about $100 in Claude tokens, which he puts at about 10 times a normal Claude Code session per unit of time. A week spent building DoltLite, a SQLite fork with Dolt-style storage, cost $3,000. Two weeks building a MongoDB-compatible database called DumboDB cost about $6,000 in Claude API calls.

## How the agents coordinate

Gas Town's Mayor, polecats and Deacon. In the third project he split work into separate 'rigs' with separate repositories and access tokens, one group writing code and one writing tests, so the agents could not mark their own work.

## Setup

Gas Town on DoltHub's metered Anthropic account. Details are in each post.

## Limits and caveats

- The first run: the first autonomously merged pull request merged despite failing integration tests, and he stopped it.
- He says he has no confidence in the generated code. The Mayor stored GitHub access tokens in the Beads database even though the rigs were meant to be isolated, so the test-code separation cannot be trusted.
- He found bugs only by manual checking, such as indexes not saved to disk and a rewritten merge conflict resolver. Verification, he says, is the hard part.
- He says the payoff is smaller for new feature work, which he had to verify by hand.
- DoltHub has a stake in Gas Town working well with Dolt. Costs and outputs are his own accounts.

[Back to the index](../README.md)
