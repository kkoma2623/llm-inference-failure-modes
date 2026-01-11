# Failure Modes and Uncertainty of LLM Inference under Distribution Shift

## Motivation
Large language models demonstrate strong performance on standard benchmarks.
However, when deployed in real-world settings, their inference behavior often
becomes unreliable due to distribution shift, ambiguous instructions, and
resource constraints.

Rather than focusing on improving benchmark accuracy or proposing new model
architectures, this project aims to understand *how* and *why* large language
models fail during inference, especially under out-of-distribution conditions.

## Research Question
This project explores the following questions:
- How do failure modes of LLMs change under distribution shift?
- How does decoding strategy (e.g., greedy vs sampling) affect model reliability?
- Can simple uncertainty proxies reveal overconfident or unreliable generations?

## Approach
We study the inference behavior of existing large language models by:
- Designing in-distribution (ID) and out-of-distribution (OOD) prompts
- Comparing deterministic (greedy) and stochastic (sampling-based) decoding
- Categorizing failure modes such as hallucination, instruction misunderstanding, partial correctness, and overconfidence
- Analyzing output variability as a proxy for uncertainty

This project emphasizes analysis and evaluation over model training.

## Current Status
- [x] Project scope defined
- [x] ID / OOD prompt set construction
- [x] Sampling-based inference experiments
- [x] Failure mode taxonomy refinement
- [ ] Quantitative and qualitative analysis

## Goal
The long-term goal of this project is to contribute to reliable and deployable inference strategies for foundation models operating under real-world constraints.

## Prompt Design
ID and OOD prompt sets used in this project are documented in the `prompts/` directory.