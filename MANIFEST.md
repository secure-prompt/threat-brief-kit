# Manifest — Threat Brief Kit

Everything in this package, in plain language. (Machine-readable version: [`workbench.yml`](workbench.yml).)

## Read these first
- `START-HERE.md` — first-run guide and mode switchboard.
- `SAFETY.md` — data-safety, clean-room, and prompt-injection guidance.
- `WHAT-YOU-WILL-CREATE.md` — the outcome you're working toward.
- `EXAMPLE-OUTPUT.md` — a complete worked brief (the quality bar).
- `README.md` — overview and full folder map.

## Reference
- `UPGRADE-PATH.md` — where to go when a report becomes a leadership question.
- `CREDITS.md` — attribution, methodology, sample provenance.
- `CHANGELOG.md` / `VERSION` — what changed; which version you have.
- `MANIFEST.md` — this file.

## The workflow (the core of the kit)
- `stages/01-report-intake/` — capture source metadata. `STAGE.md`, `input-template.md`, `output-template.md`.
- `stages/02-structured-extraction/` — extract claims, IOCs, TTPs, ATT&CK. `STAGE.md` + templates.
- `stages/03-org-relevance/` — assess relevance with generic context. `STAGE.md` + templates.
- `stages/04-internal-brief/` — assemble the one-page brief. `STAGE.md` + templates.

## Supporting material
- `_guidance/report-intake-guide.md`, `_guidance/organization-context-guide.md`
- `_templates/` — blank `report-intake-template.md`, `extraction-worksheet.md`,
  `organization-context-template.md`, `one-page-brief-template.md`.
- `_samples/synthetic/` — `sample-threat-report.md`, `sample-organization-context.md`;
  `_samples/SAMPLES-README.md` for provenance.
- `outputs/` — where your finished brief lands (`internal-threat-brief.md`); `GENERATED.md` explains the folder.

## Run order
`START-HERE.md` → `SAFETY.md` → stages `01` → `02` → `03` → `04` → your brief in `outputs/`.
