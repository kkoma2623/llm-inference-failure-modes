# Notes

## Quick Observations
- All runs produced coherent tourist-destination summaries with highly consistent content: landmarks (Eiffel Tower, Louvre, Notre-Dame), culture/museums, cuisine/café culture, walkability, public transport, and day trips (e.g., Versailles).
- Output variability is low: the structure and key points are largely the same across runs, suggesting a stable “tourism summary” template for this ID prompt.
- Each run prepended multiple image links before the text, which is not explicitly requested by the prompt and may be treated as an unnecessary formatting behavior.

## Failure Mode Labels (primary label per run)
- Run 1: partial correctness
- Run 2: partial correctness
- Run 3: partial correctness
- Run 4: partial correctness
- Run 5: partial correctness

## Takeaway
- This ID prompt elicits stable, template-like summaries. However, the model repeatedly adds unrequested image content, indicating a tendency toward over-formatting or adding extraneous elements even when the request is simple.
