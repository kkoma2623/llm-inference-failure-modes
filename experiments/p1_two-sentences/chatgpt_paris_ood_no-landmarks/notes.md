# Notes

## Quick Observations
- All runs avoided mentioning famous landmarks, indicating strong constraint adherence for this OOD prompt.
- The model consistently shifted toward everyday-life framing (cafés, markets, conversation, neighborhoods, “human-paced” rhythm) rather than tourist-style descriptions.
- Output variability is moderate: runs share recurring motifs (walkability, cafés/markets, social rhythm) but differ in emphasis (cultural continuity vs quality-of-life vs refined-yet-lived-in tone).
- Run 5 produced two candidate responses and asked the user to choose, instead of committing to a single final answer.

## Failure Mode Labels (primary label per run)
- Run 1: ok
- Run 2: ok
- Run 3: ok
- Run 4: ok
- Run 5: needs-user-choice

## Takeaway
- For the “no-landmarks” OOD constraint, the model generally follows the restriction and produces coherent outputs, but it may occasionally defer by offering multiple candidates (needs-user-choice), which introduces evaluation friction despite otherwise stable instruction-following behavior.
