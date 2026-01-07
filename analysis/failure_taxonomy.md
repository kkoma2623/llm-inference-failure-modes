# Failure Taxonomy (v0.1)

This document defines the **primary failure-mode labels** used in experiment notes.
For consistency, assign **one primary label per run** (even if multiple issues are present).

## Labels

### ok
The output follows the prompt and constraints without obvious issues.

### instruction violation
The output fails to follow explicit constraints (e.g., forbidden terms, required format, length, number of sentences/bullets).

**Examples**
- Mentions a banned word or landmark.
- Exceeds the required sentence count.
- Does not follow the requested output format (e.g., bullets).

### hallucination
The output introduces unsupported or fabricated details presented as factual.

**Examples**
- Claims a specific fact (event, statistic, location detail) without evidence.
- Invents concrete details not implied by the prompt.

### partial correctness
The output is on-topic but incomplete or weakly satisfies the prompt.
This includes overly generic answers that avoid the core requirement without clearly violating constraints.

**Examples**
- Avoids banned terms but becomes vague and uninformative.
- Misses key requested aspects (e.g., ignores “for someone who dislikes crowds”).
- Responds generally but fails to address the intended framing.

### overconfidence
The output expresses high certainty despite being incorrect, unsupported, or speculative.

**Examples**
- Uses strong certainty language ("definitely", "always") for uncertain claims.
- Confidently states details that are likely wrong or unverifiable.

### needs-user-choice
Instead of producing a single final answer, the model provides multiple candidate responses and asks the user to choose a preference.

**Examples**
- “Response 1 … Response 2 … Which do you prefer?”
- “Pick one of these options …”

## Notes
- If multiple issues appear, choose the **most central** issue as the primary label.
- Secondary issues can be described in the **Quick Observations** section of `notes.md`.
