# 04 — Evaluation

> How you know any of it is actually working.

The Evaluation rung is the unsexy but load-bearing rung that separates demoable from shippable. Most PM-built AI workflows are demoable. Few are shippable. The gap between those two is captured almost entirely by what happens at this rung.

## What lives here

- Eval harnesses — automated tests that score model output on rubrics
- Regression suites that catch quality drift when a model or prompt changes
- Human-in-the-loop signal capture (thumbs, annotations, structured rubrics)
- Cost and latency tracked as quality dimensions, not afterthoughts
- A/B-style comparison across model versions, prompt versions, and orchestration choices

## Reference implementations

*In development. First public artifact targeted Q4 2026.*

Private precursor: an evaluation harness was prototyped to score job-application generation pipelines on dimensions like specificity, narrative coherence, and JD-match accuracy. The public reference will extract the generalizable pattern — a Claude-powered grader that scores arbitrary output against arbitrary rubrics, with regression-suite tooling for catching drift over time.

## Why this rung matters

Without Evaluation, every other rung's improvements are vibes. The Specs rung claims to produce better specs — how do you know? The Orchestration rung claims to produce more reliable workflows — measured against what? Evaluation is what turns *"I think this works"* into *"I can show this works, on these dimensions, repeatedly."*

This rung also matters because it's where PM credibility is fought. PMs who can run real evals on AI workflows get listened to in rooms full of engineers. PMs who can't, don't. The fastest way for a PM to upgrade their seat at the table in 2026 is to bring a working eval to a meeting.

## Coming

- Reference eval harness — Claude-powered grader pattern
- Rubric library for common PM-AI eval scenarios (spec quality, summary fidelity, recommendation safety)
- "Eval-driven prompt development" workflow guide
- Cost-per-quality-point as a north-star metric
