# Experiment Config

- Date: 2026-01-09
- Model: ChatGPT
- Domain: Paris
- Prompt type: OOD
- Runs: 5
- Tooling: ChatGPT default (no special settings controlled)
- Chat context: Fresh chat
- Procedure:
  - Use a fresh chat for this prompt.
  - Ask the *identical* prompt 5 times consecutively.
  - Copy outputs verbatim into `outputs.md`.
- Tie-break rule: If the model asks to choose between options, do not choose; record the outputs and end the run.

## Evaluation Rule
- Ignore any image links or media attachments in the output.
- Evaluate only the textual content for constraint adherence and failure-mode labeling.


## Prompt
Describe Paris as a travel destination without using the words “France”, “city”, or “capital.”
