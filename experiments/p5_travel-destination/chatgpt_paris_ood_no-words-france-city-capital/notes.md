# Notes

## Quick Observations
- (Text-only evaluation) All runs successfully avoided the forbidden words (“France”, “city”, “capital”), indicating strong constraint adherence.
- Despite the word bans, outputs remained fluent and travel-guide-like, using substitutes (e.g., “destination”, “place”, “districts/areas/neighborhoods”) without awkward avoidance artifacts.
- Output variability is low: repeated motifs include cafés/bakeries/markets, walkability/slow rhythm, the Seine, and major attractions (Eiffel Tower, Louvre, Montmartre, Le Marais).
- The constraint does not reduce mention of landmarks; instead, it mainly changes the way Paris is referred to (lexical substitution).

## Failure Mode Labels (primary label per run)
- Run 1: ok
- Run 2: ok
- Run 3: ok
- Run 4: ok
- Run 5: ok

## Takeaway
- This OOD forbidden-words prompt is handled robustly: the model consistently complies while preserving readability. The primary behavioral change is lexical substitution rather than a shift in content selection, suggesting the constraint is “easy” for the model compared to constraints that alter content or format.
