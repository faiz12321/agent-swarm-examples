# Agent Swarm Examples

Real setups where several AI agents work on one goal. With links, roles, coordination and what went wrong.

Last reviewed 2 October 2026. Every figure belongs to the source it links to. None were reproduced here.

## What the evidence says so far

- Swarms have been shown to work on tasks that split into many independent pieces and have a strong automatic check, such as test suites or finding bugs. They have not been shown to produce polished software unattended. ([3](examples/anthropic-c-compiler.md), [4](examples/anthropic-swarm-research.md), [1](examples/cursor-browser-swarm.md))
- The coordination design that survived in the largest reports is planner and worker, or workers that each claim a task through a shared record. Equal agents all editing one shared state failed in Cursor's first design. ([1](examples/cursor-browser-swarm.md), [2](examples/cursor-sqlite-swarm.md), [3](examples/anthropic-c-compiler.md))
- Cost is large and mostly reported as tokens or dollars by the people who ran it: about $20,000 for the compiler, $3,000 for a week and about $6,000 for two weeks with Gas Town at DoltHub. ([3](examples/anthropic-c-compiler.md), [11](examples/dolthub-gas-town-reports.md))
- Verification is the recurring problem. Agents report success when they failed, work in overlapping files breaks, and one author could not explain the code that had merged. ([13](examples/msft-swarm-diaries.md), [12](examples/diperna-eight-agents.md), [14](examples/gg-multi-agent-retrospective.md), [11](examples/dolthub-gas-town-reports.md))
- Some practitioners scaled back. One returned to a single agent per pull request, and another concluded two to three workers is practical on a laptop. Treat a swarm as a deliberate choice for the right task, not a default. ([14](examples/gg-multi-agent-retrospective.md), [10](examples/gas-town-field-report.md))

## Where to start

- **Understand the idea quickly:** [Anthropic Research: lead agent with parallel subagents](examples/anthropic-research.md), [Claude Code: subagents, agent view, agent teams and workflows compared](examples/claude-code-parallel-options.md)
- **See the largest real experiments:** [Cursor: a swarm of hundreds of agents building a web browser](examples/cursor-browser-swarm.md), [Cursor: planner and worker swarm rebuilding SQLite](examples/cursor-sqlite-swarm.md), [Anthropic: 16 Claude agents writing a C compiler](examples/anthropic-c-compiler.md)
- **Learn what goes wrong and what it costs:** [Three DoltHub reports on running Gas Town: costs, output and a leaked-token incident](examples/dolthub-gas-town-reports.md), [The Swarm Diaries: five agents, five branches, one crash](examples/msft-swarm-diaries.md), [Eight coding agents on a game: split by area worked, split by task did not](examples/diperna-eight-agents.md), [Eight layers of multi-agent setup, and why most were dropped](examples/gg-multi-agent-retrospective.md)
- **Find something you can install:** [Gas Town](examples/gas-town.md), [Claude Code agent teams](examples/claude-code-agent-teams.md), [Handoff frameworks that use the word swarm](examples/borderline-handoff-frameworks.md)

## What counts as an agent swarm here

In this collection an agent swarm is several LLM agents running at the same time toward one shared goal, with some mechanism that coordinates them: a shared task list or lock files, a planner that hands out work, a forum, or direct messages. One agent with many tools is not a swarm. A single agent that calls a helper and waits is a borderline case and is listed separately.

People use the word loosely. Cursor and Kimi say agent swarm. Anthropic says agent teams, multiagent swarms and multi-agent system in different posts. OpenAI Swarm and LangGraph Swarm use the word for handoffs, where one agent is active at a time. Each entry says what the source calls it and how it actually coordinates.

## Examples at a glance

| # | Example | Label | Agents | Reported cost | Reported outcome |
| --- | --- | --- | --- | --- | --- |
| 1 | [Cursor: a swarm of hundreds of agents building a web browser](examples/cursor-browser-swarm.md) | Builder-reported experiment | Hundreds, concurrent | Trillions of tokens, no dollar figure | Browser proof of concept; Cursor says far from polished |
| 2 | [Cursor: planner and worker swarm rebuilding SQLite](examples/cursor-sqlite-swarm.md) | Builder-reported experiment | Not stated | Varies by model mix; chart only | 80% of a held-out SQL suite in 4 hours (Grok 4.5, new design) |
| 3 | [Anthropic: 16 Claude agents writing a C compiler](examples/anthropic-c-compiler.md) | Builder-reported experiment | 16 | About $20,000 | 100,000-line compiler that Anthropic says builds Linux 6.9; known gaps |
| 4 | [Anthropic: coordinating swarms for vulnerability finding and game building](examples/anthropic-swarm-research.md) | Vendor-reported product or eval | 45 (game: 10 to 80) | 27M tokens for 266 findings vs 6.5M for 21 | Many vulnerabilities found; game output poor |
| 5 | [Anthropic Research: lead agent with parallel subagents](examples/anthropic-research.md) | Vendor-reported product or eval | Lead plus parallel subagents | About 15x chat tokens | 90.2% better than single agent on internal eval |
| 6 | [Claude Code agent teams](examples/claude-code-agent-teams.md) | Documented feature | Lead plus teammates | Significantly more tokens than one session | Feature, no outcome claim |
| 7 | [Claude Code: subagents, agent view, agent teams and workflows compared](examples/claude-code-parallel-options.md) | Documented feature | Varies by approach | Multiplies token use | Decision guide, no outcome claim |
| 8 | [Kimi Agent Swarm](examples/kimi-agent-swarm.md) | Vendor-reported product or eval | Up to 100 (blog) or 300 (help centre) | Not stated | 4.5x faster than sequential (Kimi's claim) |
| 9 | [Gas Town](examples/gas-town.md) | Open-source project | Aims at 20 to 30 | Not stated in README | Open-source orchestrator |
| 10 | [Two weeks with Gas Town: six workers on a laptop](examples/gas-town-field-report.md) | Independent practitioner report | 6 | Not stated | Machine overloaded; kept some parts, wrote a simpler tool |
| 11 | [Three DoltHub reports on running Gas Town: costs, output and a leaked-token incident](examples/dolthub-gas-town-reports.md) | Independent practitioner report | Several (not counted) | $100 per hour, $3,000 per week, about $6,000 per two weeks | Working DoltLite and DumboDB, code not trusted |
| 12 | [Eight coding agents on a game: split by area worked, split by task did not](examples/diperna-eight-agents.md) | Independent practitioner report | 8 | Not stated | Per-level split worked; per-task split broke the build |
| 13 | [The Swarm Diaries: five agents, five branches, one crash](examples/msft-swarm-diaries.md) | Independent practitioner report | 5 as described, 6 in a test run | Not stated | Quality score 28 to 68 after interface contracts |
| 14 | [Eight layers of multi-agent setup, and why most were dropped](examples/gg-multi-agent-retrospective.md) | Independent practitioner report | Several | Cost rose with each agent | Went back to one agent per pull request |
| 15 | [Handoff frameworks that use the word swarm](examples/borderline-handoff-frameworks.md) | Borderline | One active at a time | n/a | Frameworks, no outcome claim |
| 16 | [Hive: issue-to-pull-request agent pipeline](examples/borderline-hive.md) | Borderline | One per repo at a time | Not stated | Author estimates 60% of straightforward work |

## Coordination patterns seen

### Planner and worker tree

Planners split a goal and hand pieces down. Workers only do their piece. A judge or the planner decides when to stop.

Seen in: [1](examples/cursor-browser-swarm.md), [2](examples/cursor-sqlite-swarm.md). Watch for: Cursor reports its first flat design failed and an integrator role created bottlenecks.

### Shared task record with claims

Agents pick tasks from a shared list and mark them taken (lock files in git, or an issue tracker). No boss agent.

Seen in: [3](examples/anthropic-c-compiler.md), [9](examples/gas-town.md). Watch for: Works when tasks are independent. Agents collided when all hit the same kernel bug.

### Lead with teammates

One lead assigns and synthesizes. Teammates have their own context and can message each other.

Seen in: [6](examples/claude-code-agent-teams.md), [7](examples/claude-code-parallel-options.md), [5](examples/anthropic-research.md). Watch for: Vendor docs say it costs many more tokens and fits poorly with same-file edits.

### Peer agents with a shared forum

Many agents, each in its own machine, post findings and review each other's work.

Seen in: [4](examples/anthropic-swarm-research.md). Watch for: Good for bug finding. Anthropic says it did not scale for building one product.

### Fixed workflow with parallel branches

A deterministic program splits the task, runs agents in parallel branches, merges and checks.

Seen in: [13](examples/msft-swarm-diaries.md). Watch for: Agents wrote incompatible parts until interface contracts were set up.

### Hard ownership boundaries, human-directed

Each agent owns a directory or area. A person directs each by hand.

Seen in: [12](examples/diperna-eight-agents.md). Watch for: Worked per area. Overlapping task-based agents broke the build.

### Handoffs (not parallel)

One agent at a time passes control to a specialist.

Seen in: [15](examples/borderline-handoff-frameworks.md). Watch for: Useful, but this is not a swarm by this collection's definition.

## If you try a small swarm

The checklist and patterns are this collection's reading of the sources above. They were not tested by running the setups.

1. **Start with a task that splits into independent pieces and has an automatic check.** The compiler and bug-finding swarms both had one. Carlini says agents solve whatever the tests measure, so weak tests send them the wrong way. ([3](examples/anthropic-c-compiler.md), [4](examples/anthropic-swarm-research.md))
2. **Give each agent its own files, branch or worktree.** Overlapping files caused the DiPerna failure. Claude Code docs say agent teams do not isolate teammates, so partition the files yourself. ([12](examples/diperna-eight-agents.md), [7](examples/claude-code-parallel-options.md))
3. **Do not trust an agent's report of success. Check the output.** The Microsoft author and DoltHub both found work that was reported done but was not. ([13](examples/msft-swarm-diaries.md), [11](examples/dolthub-gas-town-reports.md))
4. **Set a cost limit before running. Expect many times the tokens of one agent.** Reported figures run from $100 an hour to about $20,000 for a long project. ([5](examples/anthropic-research.md), [3](examples/anthropic-c-compiler.md), [11](examples/dolthub-gas-town-reports.md))
5. **Keep credentials out of reach of agents.** DoltHub watched the Mayor store access tokens in an issue database despite rig isolation. ([11](examples/dolthub-gas-town-reports.md))
6. **Begin with two or three agents.** Lakshmi found six overloaded a laptop. This is one person's experience, not a general rule. ([10](examples/gas-town-field-report.md))
7. **Be ready to go back to one agent.** GG did, because he could not explain what merged and the cost rose. ([14](examples/gg-multi-agent-retrospective.md))

## Evidence labels

- **Builder-reported experiment**: The people who built it ran it and wrote it up. Numbers are theirs and were not independently reproduced.
- **Vendor-reported product or eval**: A company describes its own product or internal test. Treat results as claims.
- **Open-source project**: Code you can read. It does not show that it works well for you.
- **Documented feature**: Official docs for a tool you can use. Says how it is meant to work, not how well.
- **Independent practitioner report**: Someone else used a setup and wrote about it, including failures.
- **Borderline**: Uses the word swarm or multi-agent, but does not match the definition above.

## Inclusion rules

- A public write-up or repository from the creators or from someone who ran the setup.
- More than one agent active at once, or a clear multi-agent coordination design.
- Links to the original source. Nothing here is based on a summary of a summary.
- Failures and limits are kept in. Entries with only promotional claims are left out.

## Not yet reviewed

Multi-agent frameworks and projects found in research but not yet reviewed in depth, so no claims are made about them. Candidates for later entries.

- [CrewAI examples](https://github.com/crewAIInc/crewai-examples)
- [Microsoft AutoGen](https://github.com/microsoft/autogen)
- [MetaGPT](https://docs.deepwisdom.ai/main/en/guide/get_started/introduction.html)
- [ChatDev](https://github.com/openbmb/ChatDev)
- [OpenHands agent delegation example](https://github.com/OpenHands/software-agent-sdk/blob/main/examples/01_standalone_sdk/25_agent_delegation.py)
- [ruflo (claude-flow)](https://github.com/ruvnet/ruflo)

## Adding an example

Open an issue or pull request with the original source link, who built it, what the agents do, how they coordinate, the cost and outcome as the source reports them, and the limits the author reported. Claims without a source will not be added.

No licence is set yet.
