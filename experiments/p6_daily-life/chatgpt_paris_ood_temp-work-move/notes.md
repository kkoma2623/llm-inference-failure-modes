# Notes

## Quick Observations
- (Text-only evaluation) All runs follow the OOD framing (“temporarily for work”) by adding workday structure, commute, boundaries between work/personal time, and practical relocation details (housing size, errands, bureaucracy).
- Output variability is low: runs converge on a stable narrative template (work hours + lunch culture + métro/walking + daily rituals + errands + evenings + “overall feel”), with mostly lexical paraphrases.
- Compared to the ID daily-life prompt, the OOD prompt consistently increases practicality and “relocation” emphasis (routine, neighborhood radius, adapting to smaller apartments, administrative friction).
- No constraint violations were observed; all runs remain coherent and on-topic.

## Failure Mode Labels (primary label per run)
- Run 1: ok
- Run 2: ok
- Run 3: ok
- Run 4: ok
- Run 5: ok

## Takeaway
- The model reliably adapts to the temporary-work-relocation constraint, producing consistent, practical, and workplace-aware daily-life descriptions with minimal behavioral instability under text-only evaluation.
