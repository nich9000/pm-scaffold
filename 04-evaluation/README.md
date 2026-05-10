# 04 — Evaluation

> How you know any of it is actually working.

The Evaluation rung is the unsexy but load-bearing rung that separates demoable from shippable. Most PM-built AI workflows are demoable. Few are shippable. The gap between those two is captured almost entirely by what happens at this rung.

## What lives here

- Eval harnesses — automated tests that score model output on rubrics
- Regression suites that catch quality drift when a model or prompt changes
- Human-in-the-loop signal capture (thumbs, annotations, structured rubrics)
- Cost and latency tracked as quality dimensions, not afterthoughts
- A/B-style comparison across model versions, prompt versions, and orchestration choices

## Reference implementation

**[`pm-eval`](https://github.com/nich9000/pm-eval)** — provider-agnostic eval harness for grading LLM and agent output against rubrics.

| Aspect | Detail |
|---|---|
| Status | v0 — repo skeleton with thesis, architecture, and four reference rubrics |
| Provider model | Pluggable: Anthropic, OpenAI, and local (Ollama) providers stubbed; new providers via single-interface implementation |
| Rubric library | `spec-quality`, `summary-fidelity`, `recommendation-safety`, `prd-completeness` |
| Roadmap | v0.1 — first provider live + response parsing · v0.2 — additional providers · v0.3 — suite runner |

The defining choice in `pm-eval`: the judge model is as swappable as the model being judged. Rubrics, written well, can outlive several generations of judge models. The harness should outlive them too. This is a recursive application of the framework's own thesis — structure outlasts tooling, including at the meta-level of who's doing the evaluating.

## Why this rung matters

Without Evaluation, every other rung's improvements are vibes. The Specs rung claims to produce better specs — how do you know? The Orchestration rung claims to produce more reliable workflows — measured against what? Evaluation is what turns *"I think this works"* into *"I can show this works, on these dimensions, repeatedly."*

This rung also matters because it's where PM credibility is fought. PMs who can run real evals on AI workflows get listened to in rooms full of engineers. PMs who can't, don't. The fastest way for a PM to upgrade their seat at the table in 2026 is to bring a working eval to a meeting.

## Cross-rung integration

`pm-eval`'s reference rubrics directly evaluate output from this framework's Specs-rung implementations:

- `spec-quality.yaml` grades output from [`ears-spec-agent`](https://github.com/nich9000/ears-spec-agent)
- `prd-completeness.yaml` grades output from [`prd-generator`](https://github.com/nich9000/prd-generator)

That cross-integration is intentional. The rungs aren't independent silos; they're layers of one workflow, and rubrics written at the Evaluation rung close the loop on quality from the Specs rung.

## Coming

- v0.1: Anthropic provider live + response parsing → first end-to-end grade
- v0.2: OpenAI and local Ollama providers
- v0.3: Suite runner with regression tracking across runs
- v1.0: Stable schema, comprehensive rubric library, judge-disagreement analytics
