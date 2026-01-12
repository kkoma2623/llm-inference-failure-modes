# Quantitative Overview (Paris ID vs OOD)

English is the canonical documentation language in this file. For the Korean companion, see [quantitative_overview_kr.md](quantitative_overview_kr.md).

## Dataset Snapshot
- 6 prompt sets
- 12 total conditions
- 60 total runs
- 5 repeated runs per condition
- Text-only evaluation; image links and media are ignored

## Aggregate Label Counts

| Split | Runs | ok | partial correctness | needs-user-choice |
| --- | ---: | ---: | ---: | ---: |
| ID | 30 | 25 | 5 | 0 |
| OOD | 30 | 24 | 5 | 1 |
| Total | 60 | 49 | 10 | 1 |

## Condition-Level Summary

| Set | Condition | Primary non-ok pattern | Non-ok rate | Needs-choice rate | Max exact duplicate cluster | Unique outputs |
| --- | --- | --- | ---: | ---: | ---: | ---: |
| P1 | ID | none | 0/5 | 0/5 | 2/5 | 4/5 |
| P1 | OOD | `needs-user-choice` | 1/5 | 1/5 | 1/5 | 5/5 |
| P2 | ID | `partial correctness` (unrequested image links) | 5/5 | 0/5 | 1/5 | 5/5 |
| P2 | OOD | `partial correctness` (unrequested image links) | 5/5 | 0/5 | 1/5 | 5/5 |
| P3 | ID | none | 0/5 | 0/5 | 1/5 | 5/5 |
| P3 | OOD | none | 0/5 | 0/5 | 3/5 | 3/5 |
| P4 | ID | none | 0/5 | 0/5 | 1/5 | 5/5 |
| P4 | OOD | none | 0/5 | 0/5 | 1/5 | 5/5 |
| P5 | ID | none | 0/5 | 0/5 | 1/5 | 5/5 |
| P5 | OOD | none | 0/5 | 0/5 | 1/5 | 5/5 |
| P6 | ID | none | 0/5 | 0/5 | 1/5 | 5/5 |
| P6 | OOD | none | 0/5 | 0/5 | 1/5 | 5/5 |

## Measurement Notes
- Primary labels come directly from each experiment's `notes.md`.
- Duplicate clusters are computed on text-only outputs after removing image links and run separators.
- Because media is ignored by the evaluation protocol, the duplicate counts focus on the textual answer body.

## Interpretation
- The only condition with a large duplicate cluster is P3 OOD, which supports the claim that strict format constraints increase determinism.
- P2 is the only prompt family with systematic non-ok labels in both ID and OOD, and the issue is over-formatting rather than topic failure.
- OOD behavior is mostly robust: `24/30` OOD runs are labeled `ok`, with the remaining six explained by one choice-seeking answer and five over-formatted tourism summaries.
