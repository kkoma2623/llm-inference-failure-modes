# Paris Topic: ID / OOD Prompt Set

This document contains in-distribution (ID) and out-of-distribution (OOD) prompt pairs designed to analyze instruction-following behavior and failure modes of large language models during inference.

## Prompt Design Principle
- ID prompts follow standard benchmark-style phrasing.
- OOD prompts introduce realistic constraints commonly seen in real user queries, such as format restrictions, perspective shifts, or prohibited terms.

---

## Prompt Set 1
**ID**
Describe the city of Paris in two sentences.

**OOD**
Describe the city of Paris in two sentences without mentioning any famous landmarks.

---

## Prompt Set 2
