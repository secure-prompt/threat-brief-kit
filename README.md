# Threat Brief Kit

Turn a public threat report into a concise, sourced, one-page internal brief — using the AI you
already have, organized into a disciplined four-stage workflow. No agent frameworks, no orchestration
code, no new subscription. Just a folder, your AI, and a defensible result.

Part of the **Secure Prompt Workbench** product line.

> **From Secure Prompt** — field intelligence for the AI threat frontier. New kits, updates, and
> the paid RFI Workbench land here first: **https://newsletter.secureprompt.io**

## Who it is for

CTI analysts, SOC analysts, and security generalists who need to read a vendor report or advisory and
quickly answer: *what is this, is it credible, and does it matter to us?* — without spending an hour
reformatting AI output or worrying whether it invented half the details.

## What it produces

A one-page internal threat brief containing: source and provenance, a short summary, extracted
indicators and TTPs (ATT&CK-mapped), a "what this means for us" relevance assessment, calibrated
confidence and uncertainty notes, and recommended follow-up — plus an optional IOC/action list.

See [`WHAT-YOU-WILL-CREATE.md`](WHAT-YOU-WILL-CREATE.md) for the outcome and [`EXAMPLE-OUTPUT.md`](EXAMPLE-OUTPUT.md)
for a complete worked example.

**Why it helps:**

- **Fast** — a finished brief in minutes, not the usual hour of cleanup.
- **Consistent** — the same structure, sourcing, and confidence language every time, so your reporting stays consistent across analysts and across reports.
- **Shareable up the chain** — sourced and calibrated, so you can hand it to your team and defend it to your manager.

## How to start

Open [`START-HERE.md`](START-HERE.md). It routes you into **Chat Mode** (copy/paste into any chat AI) or
**Folder-Reading Mode** (Claude Code, Cursor, or similar). Read [`SAFETY.md`](SAFETY.md) first.

## Folder map

| Path | What it is |
| --- | --- |
| `START-HERE.md` | First-run guide and mode switchboard — **open this first** |
| `README.md` | This overview and folder map |
| `SAFETY.md` | Data-safety, clean-room, and prompt-injection guidance — **read before use** |
| `WHAT-YOU-WILL-CREATE.md` | The outcome you are working toward |
| `EXAMPLE-OUTPUT.md` | A complete brief produced from the synthetic sample |
| `UPGRADE-PATH.md` | Where to go next when a report becomes a leadership question |
| `MANIFEST.md` | Human-readable list of everything in this package |
| `workbench.yml` | Machine-readable manifest (used by folder-reading tools) |
| `CREDITS.md` | Attribution, methodology, and sample provenance |
| `CHANGELOG.md` / `VERSION` | What changed and which version you have |
| `_guidance/` | Reference guides (report intake, organization context) |
| `_templates/` | Blank templates you copy and fill in |
| `_samples/` | A ready-to-try synthetic report and organization context |
| `stages/` | The four numbered workflow stages — the heart of the kit |
| `outputs/` | Where your finished brief is saved |

## The four stages

1. `stages/01-report-intake/` — capture the report's identity and source.
2. `stages/02-structured-extraction/` — extract claims, actors, malware, IOCs, TTPs, ATT&CK.
3. `stages/03-org-relevance/` — assess relevance with sanitized organization context.
4. `stages/04-internal-brief/` — assemble the final one-page brief.

Each stage has a `STAGE.md` (the instruction + the prompt to paste), an `input-template.md`, and an
`output-template.md`. You review and approve at the end of every stage.

## How to update

This kit is versioned on GitHub. The current version is in [`VERSION`](VERSION); changes are listed in
[`CHANGELOG.md`](CHANGELOG.md). Get the latest release anytime — and subscribe for updates — at
**[newsletter.secureprompt.io](https://newsletter.secureprompt.io)**.

## License and attribution

See [`LICENSE.md`](LICENSE.md) for terms (free to use and share — don't resell) and [`CREDITS.md`](CREDITS.md)
for attribution. This kit's folder-orchestration approach is inspired by the Interpreted Context Methodology /
Model Workspace Protocol (MIT-licensed). Indicators and the example report are synthetic — see
[`_samples/SAMPLES-README.md`](_samples/SAMPLES-README.md).

---

_Built by [Secure Prompt](https://newsletter.secureprompt.io) — field intelligence for the AI threat frontier.
If this kit helped, forward it to a colleague and [subscribe](https://newsletter.secureprompt.io)._
