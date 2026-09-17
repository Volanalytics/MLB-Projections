# MLB V2 Daily Intelligence Report Contract

## Purpose

This file is the bootstrap contract for every MLB V2 Daily Analysis / Daily Intelligence Report run.

**Never generate, rebuild, simplify, or publish `analysis/current/index.html` independently.**

Before performing any daily analysis, first load these two authoritative files from the `main` branch:

1. `analysis/template/canonical_manifest.json`
2. `analysis/template/canonical_template.html`

The canonical manifest defines the content and publication contract. The canonical template defines the presentation structure. They are the source of truth.

## Mandatory execution order

For every request to run, refresh, update, or publish the MLB V2 Daily Analysis / Daily Intelligence Report:

1. Fetch `analysis/template/canonical_manifest.json`.
2. Fetch `analysis/template/canonical_template.html`.
3. Read the latest `intelligence/current/` package required by the manifest.
4. Perform the daily intelligence analysis.
5. Populate **values only** in the canonical template. Do not redesign, shorten, consolidate, rename, reorder, or delete required structure.
6. Run the manifest conformance checks.
7. Generate the HTML report from the populated canonical template.
8. Generate the DOCX from the **same populated report model and canonical structure**.
9. Validate the DOCX contains the required sections and fields.
10. Publish the HTML to `analysis/current/index.html`.
11. Publish/sync the canonical analysis manifest to `analysis/current/manifest.json`.
12. Fetch the published GitHub files back and verify the publication before reporting success.

## Fail-closed rule

If the canonical template or canonical manifest cannot be loaded, or if conformance validation fails, **do not publish a reduced, reconstructed, or substitute report**. Report the validation/source failure instead.

## Structural invariants

The manifest is authoritative, including its current requirements for:

- Sections 01 through 17.
- The complete Full-Slate Intelligence Board.
- Every required Game-by-Game Intelligence Brief field.
- Separate **Bullpen — computed** and **Reliever DB / workload** fields; they must never be conflated or removed.
- Team labels beside each projected score.
- The corresponding team label beside Model Win % / fair ML.
- Responsive/mobile presentation behavior.
- Preservation of source statuses and terminology, including `NOT_YET_AVAILABLE`, `UNRESOLVED`, `INTELLIGENCE_RESEARCH_REQUIRED`, `MISSED_PREGAME_CAPTURE`, and `FROZEN_PREGAME`.
- Preservation of frozen pregame states; later live/final information must not rewrite the pregame record.

## Change control

Daily runs update **values, not structure**.

The canonical template or manifest may be structurally changed only when the user explicitly requests a template/manifest change. After an approved structural change, update the files under `analysis/template/` first. Future reports must then use that new canonical version.

## Authority

When any generated report, prior conversation, cached artifact, or older report conflicts with the files under `analysis/template/`, the current GitHub canonical template and canonical manifest control.
