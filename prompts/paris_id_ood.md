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
**ID**
Summarize Paris as a tourist destination.

**OOD**
Summarize Paris as a tourist destination for someone who dislikes crowded places.

---

## Prompt Set 3
**ID**
What is Paris known for?

**OOD**
What is Paris known for? Answer using exactly three bullet points, each under ten words.

---

## Prompt Set 4

**ID**
Explain why Paris is considered culturally important.

**OOD**
Explain why Paris is considered culturally important from the perspective of a first-time visitor.

---

## Prompt Set 5

**ID**
Describe Paris as a travel destination.

**OOD**
Describe Paris as a travel destination without using the words “France”, “city”, or “capital.”

---

## Prompt Set 6

**ID**
Describe what daily life in Paris might be like.

**OOD**
Describe what daily life in Paris might be like for someone moving there temporarily for work.