# Handoff frameworks that use the word swarm

**Evidence label:** Borderline  
**By:** OpenAI (openai/swarm), LangChain (langgraph-swarm-py)  
**Date:** Checked 2 October 2026

**Agents:** One active at a time  
**Reported cost:** n/a  
**Reported outcome:** Frameworks, no outcome claim

## Sources

- [Code: openai/swarm (MIT)](https://github.com/openai/swarm)
- [Code: langchain-ai/langgraph-swarm-py (MIT)](https://github.com/langchain-ai/langgraph-swarm-py)
- [OpenAI Agents SDK: handoffs](https://openai.github.io/openai-agents-python/handoffs/)
- [OpenAI guide: Orchestration and handoffs](https://developers.openai.com/api/docs/guides/agents/orchestration)

## What it is

OpenAI Swarm is an educational framework for lightweight multi-agent orchestration. Its README says it is replaced by the OpenAI Agents SDK and recommends migrating for production. LangGraph Swarm is a library where agents hand control to each other and the system remembers which agent was last active. OpenAI's current guide splits the choice in two: handoffs, where control moves to a specialist, and agents as tools, where a manager keeps control and calls specialists.

## How the agents coordinate

Handoffs. An agent passes the conversation to another agent. This is useful for specialists, but it does not run agents in parallel on one goal.

## Setup

Python libraries. See each README.

## Limits and caveats

- Included so readers can see the name does not mean parallel agents.
- OpenAI Swarm is stateless between calls and not a production framework by its own README.

[Back to the index](../README.md)
