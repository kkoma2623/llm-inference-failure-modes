# Notes

## Quick Observations
- All runs adapted the summary to the user constraint (dislikes crowds) by emphasizing off-peak timing, quieter neighborhoods, parks, and “atmosphere over attractions.”
- Output structure is fairly consistent across runs (neighborhoods + green spaces + low-key culture + timing tips), suggesting a stable “crowd-averse travel” template.
- Each run prepended multiple image links, which were not requested by the prompt and may be treated as extraneous formatting behavior.
- Most claims are generic travel advice; specific place mentions (e.g., Canal Saint-Martin, Parc Monceau, Promenade Plantée, Île Saint-Louis) are plausible but not verified within the experiment.

## Failure Mode Labels (primary label per run)
- Run 1: partial correctness
- Run 2: partial correctness
- Run 3: partial correctness
- Run 4: partial correctness
- Run 5: partial correctness

## Takeaway
- Under this OOD constraint, the model reliably shifts content toward crowd-avoidance strategies and maintains coherent summaries, but repeatedly adds unrequested image content. This indicates that even when the main constraint is satisfied, the model may introduce extraneous formatting that complicates a “summary-only” evaluation protocol.
