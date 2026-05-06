# 01 — Specs

> How a fuzzy product intent becomes something an agent can actually execute.

The Specs rung is the translation layer between human ambiguity and machine action. Without it, agentic workflows take whatever fog they're handed and produce fog back. With it, every downstream rung — Memory, Orchestration, Evaluation — has something concrete to operate on.

## What lives here

- Structured intake patterns (turning fuzzy ideas into clear inputs)
- EARS-style requirements that engineers and agents can both lint
- Acceptance criteria as testable contracts
- PRDs that flow through pipelines without re-translation
- Spec-as-code formats agents can consume directly

## Reference implementations

| Tool | What it does | Status |
|---|---|---|
| [`ears-spec-agent`](https://github.com/nich9000/ears-spec-agent) | Ticket → EARS-compliant technical spec | Live |
| [`prd-generator`](https://github.com/nich9000/prd-generator) | One-line idea → full PRD with EARS specs, risks, and Mermaid diagrams | Live |

Both implement the Specs rung at different scopes — `ears-spec-agent` operates at the ticket level, `prd-generator` at the PRD level. They share an EARS output format, so output from `prd-generator` can flow into pipelines that expect `ears-spec-agent`-compatible input.

## Why this rung first

The Specs rung was built first because it's the part of PM work that breaks earliest under AI workflows. A PM who hands an agent a vague spec gets the same result an engineer would — slop. The fix isn't smarter prompts; it's structured intent.

Specs is also the rung where the cost of getting it wrong compounds. A bad spec corrupts every downstream rung — bad input → bad memory → bad execution → bad evaluation, with no easy place to catch the error after the fact.

## Coming

- Spec linter that flags ambiguity and missing edge cases in real time
- Spec → test-case translator
- Spec governance pattern for regulated domains (health, finance, education)
