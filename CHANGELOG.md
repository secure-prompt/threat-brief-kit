# Changelog — Threat Brief Kit

All notable changes to this product. Entries are grouped by type. Versioning: patch = copy/sample fixes,
minor = non-breaking additions, major = renamed stages / changed contracts / changed outputs.

## v0.2.2 — 2026-07-04

Polish nits from a second external review (no functional change).

- `MANIFEST.md` now lists `LICENSE.md` (it was a required file the plain-language manifest omitted).
- `UPGRADE-PATH.md` fixed the garbled high-intent CTA ("…issue to ask about a custom workspace…").
- `CREDITS.md` License section now links to `LICENSE.md` explicitly.
- Standardized the brand tagline to "field intelligence for the AI threat frontier" (README header + footer now match).

## v0.2.1 — 2026-07-04

Launch-readiness pass from an external review of the packaged kit.

**Product changes**
- Added **funnel links** throughout (README header + footer, UPGRADE-PATH, EXAMPLE-OUTPUT) so anyone who
  finds or is forwarded the kit has a path back to Secure Prompt. Canonical: https://newsletter.secureprompt.io
- Added **`LICENSE.md`** (Secure Prompt Free Use License): free to use, share, and adapt for internal use;
  no resale; keep attribution. Resolves the "no stated terms" gap.
- Refined copy: dropped long time-claims ("~20–30 min") in favor of "in minutes"; added the
  share-with-your-team-and-defend-to-your-boss and consistency benefits.

**Integrity fixes**
- Removed `OWNERS.md` from `workbench.yml` `required_files` — it is builder-only and not shipped, so a
  folder-reading agent validating the manifest no longer hits a missing required file.
- Flipped `validation_status` from `draft` to `released` to match the "pre-launch proof met" state.

**Breaking changes**
- None (additive).

## v0.2.0 — 2026-07-03

Improvements from the first real dogfood run (CISA AA24-109A / Akira). See
`validation/completed-runs/threat-brief-kit/run-2026-07-03-cisa-akira/RUN-NOTES.md` in the builder repo.

**Stage Contract changes**
- Stage 2 (Structured Extraction): added a first-class **exploited-vulnerabilities (CVE)** field — for
  exploit-driven threats the specific CVEs are the most decision-relevant output.
- Stage 2: added **IOC-volume guidance** — on reports with many indicators, extract a high-signal subset
  and link the source for the full set instead of transcribing dozens of hashes.
- Stage 4 (Internal Brief): brief now carries an optional **Exploited vulnerabilities** line and a
  **source-reliability cue** (weight a government/multi-partner advisory differently from a vendor blog; note IOC age).

**Sample changes**
- Added a curated public-source dogfood run (CISA Akira advisory) as pre-launch proof; `validation.yml`
  pre-launch-proof status moved from "pending" to "met".

**Breaking changes**
- None (additive; existing workflow unchanged).

## v0.1.0 — 2026-06-21

First complete build of the Threat Brief Kit.

**Product changes**
- Four-stage workflow: report intake → structured extraction → organization relevance → internal brief.
- Dual-mode usage (Chat Mode and Folder-Reading Mode) documented in `START-HERE.md`.
- Full product wrapper: `README`, `WHAT-YOU-WILL-CREATE`, `EXAMPLE-OUTPUT`, `UPGRADE-PATH`, `MANIFEST`.

**Stage Contract changes**
- All four stages implemented on Stage Contract v1 with explicit human-review gates and mutation rules.

**Sample changes**
- Added synthetic sample threat report and synthetic organization profile.
- Added complete worked example brief (`EXAMPLE-OUTPUT.md`, `outputs/internal-threat-brief.md`).

**Safety / credits changes**
- Added `SAFETY.md` (sensitive-data, clean-room, prompt-injection guidance).
- Added `CREDITS.md` with ICM/MWP and MITRE ATT&CK attribution and synthetic-sample disclosure.

**Breaking changes**
- None (initial release).
