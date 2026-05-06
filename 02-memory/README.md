# 02 — Memory

> How context persists across runs, sessions, and people.

The Memory rung is the discipline of treating institutional knowledge as a first-class artifact, not a side effect. Every PM has lost work to a fresh chat window. Every team has lost decisions to a Slack thread that scrolled out of view six months ago. Memory is what fixes that — for both humans and the agents working alongside them.

## What lives here

- Persistent context stores agents can read and write
- Session continuity patterns (what carries forward, what doesn't)
- Decision logs, design rationale, "why we did it this way" capture
- Cross-system memory — context that's useful in Linear, Slack, Confluence, and the PM's brain at the same time
- Long-context vs. retrieval — when to use which

## Reference implementations

*In development. First public artifact targeted Q3 2026.*

In the meantime, parts of this rung are already implemented inside [`prd-generator`](https://github.com/nich9000/prd-generator)'s context-passing between agents — the orchestrator preserves framing across six agent calls so each one operates on the same shared mental model. That's a working memory primitive at the workflow level, even though it's currently packaged as part of an orchestration pipeline.

## Why this rung matters

Most PM "memory" today is human memory. That doesn't scale. As soon as an agent enters the workflow, every decision a human made implicitly has to be made explicit, captured, and made accessible to the agent on its next run — or the agent re-derives the wrong answer every time.

The Memory rung is the load-bearing infrastructure for trustworthy agentic PM work. It's also where teams quietly accumulate or lose institutional advantage: organizations that build durable, queryable context stores can deploy more capable agents over time; organizations that don't keep restarting from zero.

## Coming

- Reference implementation: a persistent-memory PM workspace pattern
- Context-handoff protocol between humans and agents (and between agent runs)
- Patterns for "what to remember vs. what to summarize vs. what to forget"
