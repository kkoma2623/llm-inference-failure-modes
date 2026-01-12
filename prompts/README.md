# Prompts

English is the canonical documentation language in this directory. For the Korean companion, see [README_kr.md](README_kr.md).

## Purpose
This directory contains the canonical prompt sets used to probe inference behavior under distribution shift.

## Available Prompt Set
- [`paris_id_ood.md`](paris_id_ood.md): English prompt pairs for the current Paris-domain study
- [`paris_id_ood_kr.md`](paris_id_ood_kr.md): Korean companion for the same prompt pairs

## Design Notes
- ID prompts use straightforward benchmark-like wording.
- OOD prompts introduce realistic user constraints such as perspective shifts, format restrictions, or forbidden terms.
- The current repository focuses on one domain so that prompt framing, repeated runs, and failure labels stay easy to compare across sets.
