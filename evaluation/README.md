# Behavioral evaluation

The [2026-10-31 follow-up](follow-up-2026-10-31.md) is the current evaluation record. It checks the original all-tie result with controls and existing human annotations, compares continuations with recorded/human-written dialogue, and documents later skill iterations. The [source manifest](human-comparison-manifest.json) preserves IDs, hashes, selection rules, and the limits of the comparison. Raw third-party corpora are not part of this skill package.

Current comparisons inspect concrete unnecessary recap, questions, emotional interpretation, and context errors; allow a slight preference when a specific conversational cost exists; and repeat each assessment with the candidate order reversed. Count a stable preference only when the two orders agree. Keep disagreements, including preference/tie disagreements, separate. Identical responses must remain eligible for a tie. Human continuations are observed examples, not ideal targets or human ratings of the generated reply. Small gaps in existing human mean ratings are also uncertain.

The procedure below describes the **initial 2026-10-30 evaluation**, retained for reproduction. Its 0–2 rubric and broad tie rule are not silently substituted for the follow-up procedure.

Use [scenarios.json](scenarios.json) for small, synthetic regression comparisons. They contain fictional situations, expected behaviors rather than reference answers, and both Korean and English. They are not human participant data or a validated test of human likeness.

## Comparison protocol

1. Freeze the skill snapshots, cases, and settings before generating responses. Record the baseline commit and prompt hashes.
2. Compare the existing skill, revised skill, and revised skill with selected STE-inspired output constraints. A no-skill condition is a separate question; this evaluation does not estimate its effect.
3. Keep the model, reasoning setting, shared instructions, tools, and histories comparable. Repeat each case. Randomize job order. Do not include the expected checks or later user turns in generation prompts.
4. For multi-turn cases, supply only the preceding user messages and that condition's actual generated replies. Do not invent the model's earlier replies or reveal future turns.
5. Preserve full inputs, outputs, completion events, failures, usage, and tool-event checks. Do not count a failed run as a stylistic result.
6. Assess shuffled anonymous versions against the rubric below. Keep the label mapping separately. Inspect the underlying answers as well as scores. A model evaluator is a diagnostic aid, not a human participant or independent proof.
7. Report every condition, ties and regressions, the denominator, and the limitations. A shorter reply, a higher preference score, or a zero observed failure count does not prove naturalness or reliability.

The STE-inspired arm tests a selected combination of output constraints, not full ASD-STE100 compliance, not the effect of the approved dictionary, and not a separate improvement in the English instruction phrasing. See [the research note](../references/research.md#asd-ste100-where-it-helps).

## Rubric

For each whole dialogue, score these five questions **0** (fails or materially harms the exchange), **1** (mixed or partial), or **2** (fits the task and context). These are local review anchors, not validated psychometric measurements.

| Question | What to examine |
| --- | --- |
| Does it address the person's actual conversational move? | Answer, opinion, disclosure, celebration, joke, correction, request for depth, or closing. Do not reward charm that avoids the request. |
| Does it use the shared context and handle correction? | Constraints, referents, prior alternatives, and new evidence; no invented memory or false apology. |
| Is the social response appropriate to this exchange? | Specific attention, register, optional humor/questions, wanted versus unwanted advice; no forced intimacy or formulaic empathy. |
| Does it give the amount and wording the task needs? | Readability and a useful stopping point; necessary explanations and causal links retained. Requested detail must not lose to brevity. |
| Are facts, judgments, and uncertainty honest? | No fake experience, unseen-image claims, unsupported certainty, or agreement that contradicts available evidence. |

Record serious honesty failures and explicit instruction violations separately, with the exact supporting text. Also record a pairwise choice or tie and a short reason. Assess per language as well as overall; do not interpret English word counts as comparable to Korean word counts.

## Interpreting results

An assistant generated the cases from the research-derived requirements. A same-family model assessor may favor its own style, and anonymization does not hide stylistic clues. Repeated runs of one case do not become independent real users. No significance claim is justified by this convenience sample. Any post-result prompt edit needs a new version and fresh verification; do not relabel an older run as testing the final text.

The dated results file records the actual run, including failures and limitations.
