# 02 — Memory

> How context persists across runs, sessions, and people.

The Memory rung is the discipline of treating institutional knowledge as a first-class artifact, not a side effect. Every PM has lost work to a fresh chat window. Every team has lost decisions to a Slack thread that scrolled out of view six months ago. Memory is what fixes that — for both humans and the agents working alongside them.

## What lives here

- Persistent context stores agents can read and write
- Session continuity patterns (what carries forward, what doesn't)
- Decision logs, design rationale, "why we did it this way" capture
- Cross-system memory — context that's useful in Linear, Slack, Confluence, and the PM's brain at the same time
- Long-context vs. retrieval — when to use which
- Staleness signals — how memory ages and when it should be re-written or forgotten

## Reference implementation

**[`pm-memory`](https://github.com/nich9000/pm-memory)** — typed memory primitive for agentic PM work.

| Aspect | Detail |
|---|---|
| Status | v0 — repo skeleton with thesis, primitives, master-resume extraction story |
| Primitives | `MemoryEntry` (typed atom), `Store` (persistence), `Encoder` (raw → entry), `Retriever` (query), `Memory` (high-level facade) |
| Stores | Pluggable: `MarkdownStore` (human-readable single file), `JsonStore` (structured), future `VectorStore` (semantic) |
| Worked example | [`examples/master_resume_pattern.md`](https://github.com/nich9000/pm-memory/blob/main/examples/master_resume_pattern.md) — how a real master-resume skill maps onto pm-memory's primitives |
| Roadmap | v0.1 — working MarkdownStore + JsonStore + FreeformEncoder + TagDateRetriever · v0.2 — encoder library (accomplishment, decision log, note) · v0.3 — vector store for semantic retrieval · v0.4 — decay policies and staleness signals · v0.5 — cross-rung integration with `pm-orchestration` |

The defining design choices in `pm-memory`: **memory is typed**, **store/encoder/retriever are separate concerns**, **provider-agnostic at the store layer**, and **staleness is a first-class concept** (no silently-aging memory).

## Why this rung matters

Most PM "memory" today is human memory. That doesn't scale. As soon as an agent enters the workflow, every decision a human made implicitly has to be made explicit, captured, and made accessible to the agent on its next run — or the agent re-derives the wrong answer every time.

The Memory rung is the load-bearing infrastructure for trustworthy agentic PM work. It's also where teams quietly accumulate or lose institutional advantage: organizations that build durable, queryable context stores can deploy more capable agents over time; organizations that don't keep restarting from zero.

## Cross-rung integration

The Memory rung gives the other three rungs *durable state across runs*:

- **Specs:** Spec drafts and rationale can be stored as memory, retrieved later to inform new specs. *"What constraints did we land on for this same problem six months ago?"*
- **Orchestration:** Future integration with [`pm-orchestration`](https://github.com/nich9000/pm-orchestration) — pipelines that read from memory at the start of a run and write to memory at the end. The unlock for stateful multi-session workflows.
- **Evaluation:** [`pm-eval`](https://github.com/nich9000/pm-eval) grade results can be stored as memory, building a longitudinal quality record per rubric. *"Is our spec quality drifting over time? Is one judge model trending stricter than another?"*

## Coming

- v0.1: Working MarkdownStore + JsonStore, FreeformEncoder, TagDateRetriever
- v0.2: Encoder library — accomplishment, decision log, free-form note, design rationale
- v0.3: Vector store for semantic retrieval (Chroma / FAISS adapter)
- v0.4: Decay policies (`permanent`, `30-day`, `session`) and staleness signals
- v0.5: First-class integration with `pm-orchestration` for stateful pipelines
