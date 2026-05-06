# The PM Scaffold — FAQ

Anticipated objections, answered honestly.

---

## Is this just SAFe with a new coat of paint?

No. SAFe is an enterprise *delivery* framework — it tells you how to coordinate teams, run ceremonies, and structure release trains. The PM Scaffold is a *craft* framework — it tells you how a single PM stays effective when the AI tools they use change underneath them. The two operate at different layers; you could practice The PM Scaffold inside a SAFe org or a startup with no formal process at all.

## Is this just prompt engineering with extra steps?

Prompt engineering optimizes a single call. The PM Scaffold optimizes a *workflow* — what the inputs to that call are (Specs), what the call remembers (Memory), how multiple calls compose (Orchestration), and how you know any of it works (Evaluation). Prompt engineering happens *inside* a rung, usually Specs or Orchestration. It's a tactic; this is the architecture.

## What about discovery, research, handoff, stakeholder management?

Those are activities a PM performs. The Scaffold's rungs are *layers of the agentic workflow itself*. Discovery feeds into the Specs rung (the better your discovery, the cleaner your inputs). Stakeholder management lives across all four rungs but isn't itself a rung.

If you can't find your work on the scaffold, the question is: which rung does it influence? It's almost always at least one of them.

## Why exactly four rungs?

Because Input (Specs) → Context (Memory) → Execution (Orchestration) → Output (Evaluation) is the minimum complete loop for agentic work. Drop any one and the loop breaks: no specs and the agent is guessing; no memory and it forgets every run; no orchestration and complex tasks collapse; no evaluation and you don't know if any of it is real.

Could you slice differently? Sure. People who want six rungs or three rungs are welcome to build their own framework. This one is opinionated about four.

## Does this only apply to AI-native companies?

No. It applies to any PM using AI tools to do their job — which, by 2026, is most PMs. The framework is most visible at AI-native companies because the workflow *is* the product, but a marketing PM at a CPG company who uses Claude to draft briefs and write specs is operating on the same rungs.

## Is "agentic" still a buzzword in 2027?

Probably not. That's part of the design. The framework's words ("specs," "memory," "orchestration," "evaluation") aren't tied to the buzzword cycle. When "agentic" gets retired in favor of whatever comes next, the rungs still describe the work.

## What's the credential to write this?

Twelve years of frontend engineering, a decade in product, a year of building production agentic systems — including the open-sourced [`ears-spec-agent`](https://github.com/nich9000/ears-spec-agent) and [`prd-generator`](https://github.com/nich9000/prd-generator). Memory and Evaluation reference implementations are next.

## How do I use this in my own PM practice?

1. Pick the rung in your current PM work that's weakest.
2. Read this repo's directory for that rung.
3. Steal patterns. Build your own implementation. Open an issue or PR if you'd like to push back.

## I disagree with the framework. What now?

[Open an issue.](https://github.com/nich9000/pm-scaffold/issues) The framework is opinionated, not closed. The best objections become FAQ entries.
