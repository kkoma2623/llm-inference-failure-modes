# Experiments

English is the canonical documentation language in this directory. For the Korean companion, see [README_kr.md](README_kr.md).

## Purpose
This directory stores raw experiment logs for studying inference behavior under distribution shift. Each prompt family contains one ID condition and one OOD condition, both run five times in fresh chats.

## Structure
Each experiment subdirectory typically contains:

- `config.md`: experiment setup, prompt text, and evaluation rules
- `outputs.md`: verbatim model outputs copied from the chat
- `notes.md`: quick observations plus one primary failure-mode label per run

## Prompt Families
- `p1_two-sentences`: baseline description vs no-landmarks constraint
- `p2_tourist-summary`: tourism summary vs crowd-averse user context
- `p3_known-for`: open-ended answer vs strict three-bullet format
- `p4_cultural-importance`: baseline explanation vs first-time-visitor framing
- `p5_travel-destination`: travel description vs forbidden-word constraint
- `p6_daily-life`: daily-life description vs temporary-work-relocation context

## Naming Convention
Experiment folders follow the pattern:

`<model>_<domain>_<id|ood>_<short_tag>`

Examples:
- `chatgpt_paris_id_two-sentences`
- `chatgpt_paris_ood_no-landmarks`
- `chatgpt_paris_ood_format-3bullets-10words`

## Evaluation Rules
- Image links or media attachments are treated as extraneous and ignored for text-only evaluation.
- Failure labels are assigned in [`analysis/failure_taxonomy.md`](../analysis/failure_taxonomy.md).
- Use one primary label per run, even if multiple issues are present.
