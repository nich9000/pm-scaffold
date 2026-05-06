# 03 — Orchestration

> How multi-step work gets composed without falling apart.

The Orchestration rung is the architectural choices that decide whether an agentic workflow survives complexity or collapses into prompt soup. The difference between a clever demo and a shippable system usually lives at this rung.

## What lives here

- Orchestrator-workers patterns
- Hand-offs between agents (and between agents and humans)
- Tool-use design (when to give an agent a tool vs. another agent)
- Failure-mode planning (what happens when one step in a chain breaks)
- Cost-aware routing (when to use Haiku vs. Sonnet vs. Opus per step)

## Reference implementations

*Standalone artifact in development. Targeted Q1 2027.*

A working orchestration example is already inside [`prd-generator`](https://github.com/nich9000/prd-generator) — the six-agent pipeline (Framer → Story Writer → Acceptance Writer → EARS Author → Risk Auditor → Diagrammer) is itself a reference orchestration. It's not packaged as a standalone Orchestration artifact because the framework is currently wearing the Specs hat there. The eventual standalone repo will extract that pattern into a generic, reusable orchestrator.

## Why this rung matters

A single Claude call can do impressive things. A chain of six can do production things. A chain of six that you can debug, tweak independently, and rerun in isolation — that's the difference between a demo and a tool.

Orchestration is the rung that converts cleverness into reliability. It's also where most agentic PM workflows fail in practice: people stack prompts on prompts until something breaks, then can't tell which prompt broke. A well-orchestrated workflow makes failures legible — you know which agent stumbled, on which step, with what input, and you can fix that one piece without rebuilding the whole pipeline.

## Coming

- Generic multi-agent orchestrator pattern
- Failure-handling primitives (retries, fallbacks, human-in-the-loop escalation)
- Cost-aware routing decision framework
- Orchestration anti-patterns gallery
