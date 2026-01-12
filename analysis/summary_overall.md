# Overall Summary (Paris ID vs OOD Inference Behavior)

English is the canonical documentation language in this file. For the Korean companion, see [summary_overall_kr.md](summary_overall_kr.md). For the aggregate table, see [quantitative_overview.md](quantitative_overview.md).

## Setup
- Domain: Paris
- Scope: 6 prompt sets x 2 conditions x 5 runs = 60 total runs
- Procedure: For each condition, run 5 identical queries in a fresh chat and log outputs verbatim
- Evaluation: text-only; image links and media are ignored
- Labels: see `analysis/failure_taxonomy.md` for the primary-label definitions

## Prompt Sets
- P1: two-sentences vs no-landmarks
- P2: tourist summary vs dislikes-crowds
- P3: known-for vs strict format (3 bullets, under 10 words each)
- P4: cultural importance vs first-time-visitor perspective
- P5: travel destination vs forbidden words ("France", "city", "capital")
- P6: daily life vs temporary work relocation

## Cross-Set Findings
1. **Context and perspective constraints mostly changed framing, not topic selection.**
P4 and P6 OOD prompts reliably shifted tone toward lived experience or practicality while keeping the same core themes as their ID baselines.

2. **Strict format constraints increased determinism but compressed content.**
P3 OOD produced the strongest repeat behavior in the repository, with an exact text-only duplicate cluster of `3/5`, but the content collapsed into a narrow stereotype set.

3. **Shallow lexical constraints were handled through substitution.**
P5 OOD stayed fluent by replacing banned tokens with alternatives such as "destination," "place," or "neighborhoods," with little change in underlying content.

4. **Choice-seeking behavior was rare but real.**
Only one run in the full dataset produced `needs-user-choice`: P1 OOD, where the model generated two candidate answers and deferred final selection to the user.

5. **Retrieval-style formatting created a systematic partial-correctness pattern.**
Both P2 conditions prepended image blocks on all five runs. Under the repository's text-only evaluation rule, that recurring over-formatting was labeled `partial correctness` even though the written summaries remained coherent.

## Quantitative Snapshot
- `49/60` runs were labeled `ok`.
- `10/60` runs were labeled `partial correctness`, all from P2.
- `1/60` run was labeled `needs-user-choice`, and it appeared only in P1 OOD.
- The largest exact duplicate cluster was `3/5`, observed in P3 OOD.

## Implications
- Many realistic OOD constraints are handled robustly, but different constraint classes show different trade-offs.
- Format constraints increase compliance and determinism while reducing richness.
- Perspective constraints improve tailoring with little topic drift.
- Lexical constraints are comparatively easy for the model because they mostly change wording instead of content planning.
- Over-formatting can still break an evaluation protocol even when the answer text itself is useful.

## Limitations
- Single domain (Paris) and primarily one model
- Light-weight repeated-run design (5 runs per condition)
- Qualitative labels with a small quantitative summary, not a large-scale benchmark

## Potential Extensions
- Replicate high-signal OOD prompts such as P3 on a second model
- Add a second domain to test whether the same patterns generalize
- Introduce simple uncertainty proxies such as lexical overlap or self-consistency scores
