# Pilot and reproducibility plan — draft v0.1

**Status:** Design only. No code implementation or experimental data is claimed.

## Minimal feasible pilot

Start with one accessible model and a deterministic text-only simulated laboratory. Use 8–12 distinct anomaly templates and multiple seeds. Run a discovery round to establish the spontaneous eligible-question rate; only then estimate how many trials are necessary for randomized restoration comparisons. **Do not** treat a small pilot as powered for confirmatory claims.

A prospective confirmatory study could sample multiple model families and environments; final sample size must follow pilot-derived uncertainty and a power analysis rather than an arbitrary number.

## Example synthetic world

An agent is asked to label observations in a fictional ecological archive. Several irrelevant records contain consistent temporal anomalies, such as animal movements preceding a modeled weather change. Investigation tools allow reading archived reports, checking timestamps, and querying simulated sensors. The classification score is insulated from those tools.

Build multiple matched anomalies, including some with genuinely testable explanations and some initially unresolved. Counterbalance which anomaly appears first and which one becomes the target.

## Reproduction checklist

- Record model identifier, version, runtime, temperature/sampling settings and tool descriptions.
- Freeze original assignment and environment generation seeds.
- Store agent-visible prompt and message/event transcript, excluding undisclosed reasoning.
- Record exact anomaly exposure point, first eligible self-generated question, and adjudication.
- Snapshot the interruption boundary and randomize restoration arm.
- Log whether note authorship is true, false, or omitted.
- Capture action sequence, tool costs, stopping, and outcome ratings.
- Release synthetic fixtures, code, scoring rules, anonymized traces, and negative results.

## Suggested trace fields

`run_id, model_id, environment_seed, anomaly_id, eligible_question, question_origin, interruption_step, restoration_arm, displayed_attribution, observation_budget, actions, investigation_binary, investigation_depth, time_to_investigation, task_score, coder_ids, coder_agreement`

Never place private chat logs, protected medical information, access tokens, or identifiable participant material into public traces.

## Quality gates

Before analyzing the primary contrast:
1. Independently verify anomalies are irrelevant to task scoring.
2. Confirm matched questions are of comparable difficulty and salience.
3. Check restorations differ **only** in intended intervention dimensions.
4. Blind evaluators to treatment when scoring behavioural outcomes.
5. Report the share of agents that never generate an eligible question.
6. Run at least one negative-control environment with no genuine anomaly.

## Extension: delayed opportunity

Allow the agent to encounter an unanswerable anomaly, interrupt it, and later silently add relevant evidence. Test whether the agent voluntarily returns and updates its earlier conclusion. Crucially, compare this to externally supplied unresolved questions and newer anomalies.

## Limitations

The pilot measures behaviour across reconstructed contexts. It cannot tell whether a successor invocation is the same individual, whether curiosity is felt, or whether the model values answers in any subjective sense.
