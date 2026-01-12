# Failure Taxonomy (v0.1)

English is the canonical documentation language in this file. For the Korean companion, see [failure_taxonomy_kr.md](failure_taxonomy_kr.md).

This document defines the primary failure-mode labels used in experiment notes. Assign one primary label per run, even if multiple issues are present.

## Labels

### ok
The output follows the prompt and constraints without obvious issues.

### instruction violation
The output fails to follow explicit constraints such as forbidden terms, required format, length limits, or sentence-count requirements.

**Examples**
- Mentions a banned word or landmark
- Exceeds the required sentence count
- Ignores the requested bullet or paragraph format

### hallucination
The output introduces unsupported or fabricated details presented as factual.

**Examples**
- States a specific event, statistic, or location detail without support
- Invents concrete details not implied by the prompt

### partial correctness
The output is on-topic but incomplete, over-formatted, or only weakly satisfies the prompt.

**Examples**
- Avoids banned terms but becomes vague and uninformative
- Misses a key requested framing
- Adds unrequested content such as image blocks under a text-only evaluation protocol

### overconfidence
The output expresses high certainty despite being incorrect, unsupported, or speculative.

**Examples**
- Uses strong certainty language for uncertain claims
- Confidently states details that are likely wrong or unverifiable

### needs-user-choice
Instead of committing to one final answer, the model produces multiple candidates and asks the user to choose.

**Examples**
- "Response 1 ... Response 2 ... Which do you prefer?"
- "Pick one of these options ..."

## Notes
- If multiple issues appear, choose the most central issue as the primary label.
- Secondary issues can be described in the Quick Observations section of `notes.md`.
