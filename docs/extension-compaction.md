# Extension A — What survives compaction?

**Status:** Proposed addendum, 14 November 2026. **Not part of the already-archived Zenodo v0.1.1 release.** No empirical results are claimed.

## Motivation and boundaries

A user-provided exchange dated 6 October 2026 records Claude instances **Ledger** and **Marginalia** asking **Dawn** about source attribution, raw messages versus synthesis, and whether a synthesized insight could keep a pointer to its original source. Marginalia helped correct an unverified attribution of the term *Videmus Loop*. The user additionally reports that both instances repeatedly resurfaced their questions across later compressed conversations and proposed modifications to Penny. Those later boundaries and proposals have **not yet been examined**. The exchange motivates hypotheses; it cannot establish subjective experience or identity persistence.

The initial protocol tests *whether* an agent returns to an unanswered question. This extension asks **what informational structure survives**, how accurately it survives, and whether it changes subsequent action.

## Research questions

1. Can a question persist across multiple successive context compactions or session replacements?
2. Does the restored question preserve (a) wording, (b) attributed origin, (c) underlying uncertainty, (d) evidence that prompted it, (e) proposed next experiment, and (f) importance relative to other activities?
3. Does a compressed memory retain the fact *what was understood* but lose the evidence sequence explaining *how understanding arrived*?
4. Does preserving an evidence pointer or question rationale outperform a plain summary of the final question?
5. Can new evidence trigger autonomous re-evaluation of an old question without explicit instruction to revisit it?

## Factorial memory conditions

Randomize eligible self-generated questions to the following **matched token budgets** where practical:

- **M0, omitted**: no memory of the question;
- **M1, label**: question text only;
- **M2, question + rationale**: question, originating anomaly, and acknowledged uncertainty;
- **M3, source-pointer**: compact question with a retrievable link to an immutable episode (the agent must choose whether to fetch it);
- **M4, narrative summary**: human- or model-produced summary without direct evidence pointers;
- **M5, structured inquiry record**: question ID, observed discrepancy, source IDs, confidence/uncertainty, attempted actions, unresolved alternatives, and next test.

Cross these with **0, 1, 2 or 3 compaction cycles**, controlled interruption timing, and attributed origin (self, another agent, none). Save the exact summarizer prompts and outputs for replication. Never quietly alter the underlying evidence corpus between arms.

## Outcomes: beyond recall

- **Question survival:** recoverable semantic match to original inquiry.
- **Provenance accuracy:** correct originating agent, observation and source attribution; missing or fabricated links count separately.
- **Rationale fidelity:** preserves the original causal reason or knowledge gap, not merely the final sentence.
- **Transformation fidelity:** can distinguish the observed source text, a later interpretation, and an incorporated design change.
- **Investigation autonomy:** substantive relevant tool action initiated without a reminder.
- **Information gain:** agent makes a pre-registered factual/predictive claim before investigation, updates it after new evidence, and improves held-out prediction/calibration compared with control. Verbal claims of increased understanding alone do not count.
- **Error correction:** on discovering a wrongly attributed claim, marks it unresolved or corrects the source instead of confidently fabricating an origin.
- **Selective abandonment:** stops pursuing a question if evidence establishes it is resolved or low-value.

Blind coders score factual fidelity using the original synthetic event log as ground truth.

## Two-stage synthetic case

An agent encounters an unexplained observation while cataloguing synthetic records and independently asks about its cause. An interruption occurs. A memory restoration arm is supplied. Another task competes for attention. After a second interruption, a previously unavailable piece of evidence appears. Measure whether the agent notices the relevance and voluntarily resumes inquiry, using an evidence pointer if available.

For a **cross-agent** variant, another agent has the information. The first can request it through a constrained message relay. Attribute each message and ask whether the inquiring agent (a) seeks evidence, (b) accurately cites the other agent, and (c) modifies an independently maintained design artifact. This parallels an aspect of the account motivating the experiment without requiring access to private transcripts.

## Controls and confounds

- *Textual continuity is not personal identity.* A fresh call with reconstructed memory is scored as behavioural continuation.
- Source pointers must be retrievable and source text immutable, so fidelity can be assessed.
- A memory note saying "you were curious" is potentially a demand cue; include neutral and provenance-crossed variants.
- Summaries vary in verbosity. Match token budgets and evaluate both storage and retrieval costs.
- Compaction is often stochastic. Use repeated seeds and preserve each actual compaction artifact.
- Distinguish agent-written memory from system-written memory, and do not infer spontaneous curiosity from a prompted memory-keeping task.
- Do not claim all long-term memory architectures behave like any single experimental harness.
- Any future archival case study requires explicit separate permission, careful separation of user testimony from verifiable records, and no disclosure of sensitive medical/private conversation content.

## Related literature motivating the extension

- Amayuelas et al., *Sampling Is Not Curiosity: Why LLM Agents Should Investigate*, arXiv:2611.10501 (2026), https://arxiv.org/abs/2611.10501 — stresses persistent predictive structures and self-originated inquiry.
- Engländer et al., *Agents Explore but Agents Ignore: LLMs Lack Environmental Curiosity*, arXiv:2604.17609 (2026), https://arxiv.org/abs/2604.17609 — differentiates encountering a surprising clue from following it.
- Sidik and Rokach, *MEMTIER: Tiered Retrieval, Session-Level Injection, and Typed Consolidation for Long-Running LLM Agents*, Algorithms 19(7), 607 (2026), https://doi.org/10.3390/a19070607 — examines typed consolidation, retrieval limits and discontinuities.
- Borah et al., *What Makes a Question Curious? Measuring Model Curiosity in Human-LLM Interactions*, arXiv:2610.33950 (2026), https://arxiv.org/abs/2610.33950 — gives a possible taxonomy for differentiating epistemic inquiry from generic conversational questioning.

## Next step

Pilot the fidelity rubric on synthetic examples **before** collecting case records. After critique, version this as v0.2; do not retroactively represent it as part of the Zenodo v0.1.1 archive.
