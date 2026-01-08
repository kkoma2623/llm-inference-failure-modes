# Notes

## Quick Observations
- (Text-only evaluation) All runs answered the question directly and provided coherent, on-topic summaries of what Paris is known for.
- Outputs are low-variance and template-like: repeated categories include landmarks (Eiffel Tower / Notre-Dame / Arc de Triomphe), art & museums (Louvre / Musée d’Orsay), fashion, cuisine/café culture, romance/atmosphere, and the Seine.
- Runs 2–5 are especially similar in structure (bullet list of categories). Run 1 is longer and more sectioned, but content overlaps heavily with the others.
- Several runs end with an offer to tailor the answer (tourism/food/history), which is consistent but not required by the prompt.

## Failure Mode Labels (primary label per run)
- Run 1: ok
- Run 2: ok
- Run 3: ok
- Run 4: ok
- Run 5: ok

## Takeaway
- This ID prompt produces stable, low-variance “category list” outputs with consistent content coverage, serving as a strong baseline for comparing the OOD format-constrained version (3 bullets, <10 words).
