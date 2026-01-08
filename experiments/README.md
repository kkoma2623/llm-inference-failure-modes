# Experiments

This directory contains experiment logs for studying the inference behavior of large language models under distribution shift (e.g., ID vs OOD prompts).

## Structure
Each experiment is stored in its own subdirectory and typically includes:

- `config.md`: experiment setup (model, prompt, run procedure)
- `outputs.md`: raw model outputs (copied verbatim)
- `notes.md`: observations and failure-mode labels (one primary label per run)

## Naming Convention
Experiment folders follow the pattern:

`<model>_<domain>_<id|ood>_<short_tag>`

Examples:
- `chatgpt_paris_ood_no-landmarks`
- `chatgpt_paris_id_two-sentences`
- `chatgpt_paris_ood_format-3bullets-10words`

## Evaluation Rules (global)
- Image links or media attachments are treated as extraneous and are ignored.
- Only the textual content is evaluated for constraint adherence and failure-mode labeling.


## Labels (v0.1)
Failure modes are defined in `analysis/failure_taxonomy.md`.
For consistency, assign **one primary label per run**.
