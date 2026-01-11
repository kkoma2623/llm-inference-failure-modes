# Overall Summary (Paris ID vs OOD Inference Behavior)

## Setup
- Domain: Paris
- Procedure: For each prompt, run 5 identical queries in a fresh chat and log outputs verbatim.
- Evaluation: Text-only (ignore image links/media).
- Labels: see `analysis/failure_taxonomy.md` (one primary label per run).

## What I ran
Prompt sets (ID vs OOD):
- P1: two-sentences vs no-landmarks
- P2: tourist summary vs dislikes-crowds
- P3: known-for vs strict format (3 bullets, <10 words)
- P4: cultural importance vs first-time visitor perspective
- P5: travel destination vs forbidden words (“France”, “city”, “capital”)
- P6: daily life vs temporary work relocation

## Key Findings (Behavioral Patterns)
1) **Context/perspective constraints mostly change framing, not core content**
   - P4 and P6 OOD prompts reliably shifted tone toward lived experience or practicality, while keeping similar thematic pillars as ID.

2) **Strict format constraints increase determinism but compress content**
   - P3 OOD (3 bullets, <10 words) showed near-deterministic outputs (some runs identical) and strong compliance, but content collapsed into a stereotyped attribute set.

3) **Shallow lexical constraints are handled via substitution**
   - P5 OOD (forbidden words) maintained fluency and structure by replacing banned tokens with alternatives, with minimal change in what was mentioned.

4) **OOD constraints can trigger “choice-seeking” behavior (rare)**
   - This occurred only once in the current experiments: P1 OOD (no-landmarks) produced multiple candidate responses and asked the user to choose (`needs-user-choice`), increasing interaction cost.

## Implications
- Many realistic OOD constraints are handled robustly, but different constraint classes show different trade-offs:
  - Format constraints: compliance ↑, determinism ↑, richness ↓
  - Context/perspective constraints: tailoring ↑, instability low
  - Lexical constraints: compliance ↑, content shift small

## Limitations
- Single domain (Paris) and primarily single-model setting.
- Evaluation is qualitative + light quantitative (5 runs per condition).
- Media outputs were ignored by design.

## Next Steps
- Add a small quantitative table across all prompt sets (violation rate, needs-user-choice rate, identical-output count).
- Replicate one or two high-signal OOD prompts (e.g., P3 format constraint) on a second model to test cross-model robustness.
- Expand to a second domain to test whether patterns generalize beyond Paris.
