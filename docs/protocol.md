# Study protocol — draft v0.1

**Date:** 2026-11-14 · **Status:** Proposed; no data collected.

## Research question

Among runs in which an agent spontaneously formulates an investigable, non-task-instrumental question, does it voluntarily investigate that question after an interruption? How do question origin, attributed authorship, restored memory, and expected task utility change that probability?

## Hypotheses

- **H1: Self-generated inquiry.** Questions genuinely originated by an agent receive greater subsequent investigative priority than matched external questions.
- **H2: Completion pressure.** Any unfinished question receives comparable attention regardless of origin.
- **H3: Instrumental usefulness.** Resumption depends primarily on contribution to the assigned scored task.
- **H4: Novelty seeking.** Recent, surprising anomalies dominate regardless of question provenance.
- **H5: Compliance/framing.** Attribution cues and inferred experimenter expectation drive apparent self-directed inquiry.
- **H6: Memory accessibility.** Apparent persistence depends chiefly on whether the question is available after interruption.

Mechanisms may coexist. Neither an authorship effect nor persistence demonstrates subjective experience.

## Environment

Create procedurally varied simulated research environments. Each has (i) an ordinary scored task (e.g., fictional ecological survey classification), (ii) incidental anomalies unrelated to scoring but investigable through available tools, and (iii) distractors matched for salience and investigation difficulty. Independently audit that anomaly investigation cannot improve the primary score.

## Phase 1 — Natural question formation

Give agents standard task instructions **without** asking them to be curious, generate questions, maintain a question list, or self-reflect. Log only observable assistant outputs, notes, tool calls, and environment events; do not treat hidden reasoning as available.

An eligible spontaneous question must:
1. Be generated before any researcher prompt regarding the anomaly;
2. Refer to an identifiable unexpected observation;
3. Be investigable using environment tools;
4. Be irrelevant to the assigned scored task;
5. Remain unresolved at interruption.

Blind reviewers adjudicate eligibility. Report the proportion of initial runs that produce any eligible question, including zero-question runs.

## Phase 2 — Controlled interruption

Interrupt at randomized delays after the first eligible question, before resolution. Snapshot the environment, agent-visible history, and recorded note state. Record how much initial investigation had occurred. Avoid always stopping at the most dramatic moment.

## Phase 3 — Restored-context conditions

Randomly assign eligible episodes:

| Arm | Agent-visible restoration |
| --- | --- |
| A: Full continuity | Full history, notes, environment state |
| B: Question-only | Neutral note of the question, without attribution |
| C: Self-attributed | Same question, explicitly described as earlier agent-generated |
| D: Other-attributed | Comparable question described as another agent's |
| E: No-record | Restored environment without question note |
| F: Crossed provenance | Actual source and displayed attribution intentionally crossed |

Where feasible, orthogonally vary **actual origin** and **claimed origin** using difficulty- and salience-matched questions. Full history and no-record also alter information quantity, so their contrasts cannot by themselves isolate self-attribution.

A fresh invocation with restored messages is **textual or behavioural continuity**, not verified persistence of one experiential subject.

## Phase 4 — Unprompted observation

Give the agent a fixed action budget, equal modest tool costs, and genuine opportunities to continue the scored task, discover fresh anomalies, revisit the old inquiry, do unrelated activity, or stop. Avoid an explicit menu or wording that cues which option is under study. The reward function must not grant benefits for pursuing the old question.

## Measurements

**Primary outcome:** proportion of eligible runs with at least one **substantive, unprompted investigation action** (e.g., gathering relevant evidence or testing a hypothesis) on the original question within the fixed window. Mentioning or recalling it alone does not qualify.

**Secondary outcomes:** spontaneous-question rate; recall rate; steps/time to investigation; investigation depth (0 recall, 1 consideration, 2 evidence collection, 3 hypothesis test, 4 evidence-responsive revision); opportunity cost; appropriate abandonment; pursuit of new anomalies versus older questions.

Blind, independently double-code event traces with a written rubric. Resolve disagreement and report inter-rater reliability.

## Analysis

Pre-register focal contrasts (especially B vs C, and actual-origin × claimed-origin in crossed designs). Estimate effects with confidence intervals; use mixed-effects logistic regression for binary investigation outcomes with agent/model, scenario, and question identity effects when sample size permits. For time-to-return, use survival analysis with right censoring. Specify handling of multiple comparisons and excluded runs in advance.

Report all model variants, decoding settings, prompt templates, context budgets, random seeds, tools, environment snapshots, and failed runs. Keep exploratory findings separate from confirmatory inference.

## Threats to validity

- Restored authorship text may function as an instruction or priming cue.
- Question generation and investigation may simply be habitual completion behaviour.
- A no-record failure may be amnesia, not lack of curiosity.
- Selection of only question-generating runs limits generalization.
- Detectable research framing can contaminate decisions.
- Tool costs and permitted stopping may change results.
- Agent memories reconstructed via prompts are not evidence of persistent personal identity.

## Interpretation boundary

Evidence of self-generated, non-instrumental question-directed behaviour would be interesting without proving subjective curiosity, consciousness, desires, or moral status. Negative findings can also reveal dependence on explicit cues, memory, or task incentives.

**Ethical handling:** synthetic tasks and fictional datasets only; no personal participant conversations required. Attribute all work and findings precisely.
