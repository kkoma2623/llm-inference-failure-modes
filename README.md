# Failure Modes and Uncertainty of LLM Inference under Distribution Shift

English is the canonical documentation language in this repository. Korean companion documents use the `_kr.md` suffix. For a Korean overview, see [README_kr.md](README_kr.md).

## Overview
This repository documents a small-scale research study on how ChatGPT inference behavior changes under distribution shift. The current study uses six Paris prompt pairs, each evaluated with one in-distribution (ID) prompt and one out-of-distribution (OOD) prompt, with five repeated runs per condition.

## Research Questions
- How do failure modes change under distribution shift?
- How do deterministic and stochastic behaviors show up across repeated runs?
- Can lightweight uncertainty proxies such as output variability reveal unstable or overconfident generations?

## Repository Guide
- [`prompts/paris_id_ood.md`](prompts/paris_id_ood.md): canonical prompt pairs used in the current study
- [`prompts/paris_id_ood_kr.md`](prompts/paris_id_ood_kr.md): Korean companion for the prompt set
- [`experiments/README.md`](experiments/README.md): experiment log structure and evaluation rules
- [`analysis/failure_taxonomy.md`](analysis/failure_taxonomy.md): primary failure-mode labels
- [`analysis/quantitative_overview.md`](analysis/quantitative_overview.md): aggregate table across all 60 runs
- [`analysis/summary_overall.md`](analysis/summary_overall.md): cross-prompt qualitative synthesis

## Current Status
- [x] Project scope defined
- [x] ID / OOD prompt set construction
- [x] Sampling-based inference experiments
- [x] Failure mode taxonomy refinement
- [x] Quantitative and qualitative analysis

## Headline Findings
- Perspective and context shifts mostly changed framing rather than topic selection.
- Strict format constraints increased determinism the most: the P3 OOD prompt produced an exact text-only duplicate cluster of `3/5`.
- Only one run across the full dataset produced `needs-user-choice`, and it occurred in P1 OOD.
- The P2 tourism prompts repeatedly inserted unrequested image blocks, which were labeled `partial correctness` under the text-only evaluation protocol.

## Reading Order
1. Read [`prompts/paris_id_ood.md`](prompts/paris_id_ood.md) for the prompt pairs.
2. Inspect the raw logs under [`experiments/`](experiments/README.md).
3. Review [`analysis/quantitative_overview.md`](analysis/quantitative_overview.md) for the aggregate counts.
4. Finish with [`analysis/summary_overall.md`](analysis/summary_overall.md) for the behavioral interpretation.
