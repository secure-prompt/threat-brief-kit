---
id: "04-internal-brief"
title: "Internal Brief"
contract_version: "stage-contract-v1"
owner: "human"
purpose: "Assemble the prior stages into a concise, sourced, one-page internal threat brief with calibrated confidence."
entry_criteria:
  - "Stage 1, 2, and 3 outputs exist and have been reviewed."
required_inputs:
  - path: "../../_templates/one-page-brief-template.md"
    type: "template"
  - path: "../01-report-intake/output.md"
    type: "prior-stage-output"
  - path: "../02-structured-extraction/output.md"
    type: "prior-stage-output"
  - path: "../03-org-relevance/output.md"
    type: "prior-stage-output"
allowed_context:
  - "All three prior stage outputs"
ai_task: "Assemble a one-page brief from the prior stages. Add nothing new — only synthesize what the reviewed stages contain. Preserve confidence and uncertainty."
human_review_gate: "Analyst confirms the brief is accurate, sourced, appropriately hedged, and contains no invented content, before sharing."
outputs:
  - path: "../../outputs/internal-threat-brief.md"
    type: "markdown"
output_paths:
  - "outputs/internal-threat-brief.md"
completion_criteria:
  - "Brief includes source, summary, key findings, relevance, confidence/uncertainty, and recommended follow-up."
  - "Optional IOC/action list is included or explicitly omitted."
  - "Every claim traces back to a reviewed prior stage."
failure_modes:
  - "Introducing new claims or indicators not present in Stages 1–3."
  - "Dropping the confidence/uncertainty language and sounding falsely certain."
handoff:
  next_stage: "none — final stage"
mutation_rules:
  read_only:
    - "STAGE.md"
    - "../01-report-intake/output.md"
    - "../02-structured-extraction/output.md"
    - "../03-org-relevance/output.md"
  writable:
    - "../../outputs/internal-threat-brief.md"
    - "notes.md"
---

# Stage 4 — Internal Brief

**Goal:** assemble everything you've reviewed into a clean one-page brief someone can read in two minutes
and act on. Nothing new is created here — this stage *synthesizes* the reviewed work, it does not add to it.

## What to do

1. Have your three reviewed stage outputs ready.
2. Run the prompt below (or let the agent assemble `outputs/internal-threat-brief.md`).
3. Do the final review, then save to `outputs/internal-threat-brief.md`. That's your deliverable.

## Prompt to paste into your AI

```
You are assembling a one-page internal threat brief from three reviewed analyst work products.
Do NOT introduce any new claim, indicator, actor, or recommendation. Use ONLY what is in the inputs.

Produce the brief in this structure:

# Threat Brief: [short title]
- Source: [publisher, date, link from Stage 1]
- Prepared: [today's date] | Analyst: [leave a placeholder]

## Bottom line up front (2–3 sentences)
A crisp summary: what the threat is, who it targets, and our relevance level.

## Key findings
- 4–7 bullets from the extraction. Preserve [FACT] vs [ASSESSMENT] distinctions in plain wording
  (e.g. "The vendor assesses, with moderate confidence, that...").
- If the threat is exploit-driven, name the specific CVEs and affected products here or in a short
  "Exploited vulnerabilities" line — these are usually the most decision-relevant detail.

## What this means for us
The relevance level + rationale and the most relevant TTPs, from Stage 3.

## Confidence and gaps
- State overall confidence and name what is uncertain or unconfirmed. Do not hide uncertainty.
- Include a one-line source-reliability cue: weight a government/multi-partner advisory differently from a
  single vendor blog or news article, and note IOC age if the report gives it.

## Recommended follow-up
- The actions from Stage 3, tightened to the few that matter.

## Indicators (optional)
- A short, clearly-labeled IOC list IF useful for the audience, copied exactly from Stage 2.
  Otherwise write "See source report for full indicator list."

Rules:
- Keep it to roughly one page.
- Add nothing that isn't in the inputs.
- Preserve all confidence/uncertainty language.

Then stop and wait for my review.

Stage 1 (source):
[PASTE]
Stage 2 (extraction):
[PASTE]
Stage 3 (relevance):
[PASTE]
```

## Final review checkpoint — do not skip

- [ ] **Source line** is present and correct (publisher, date, link).
- [ ] Every claim traces to a reviewed stage — **nothing new was introduced.**
- [ ] **Confidence and gaps** are stated; the brief does not sound more certain than the evidence.
- [ ] IOCs (if included) match Stage 2 exactly.
- [ ] It reads in about two minutes and a busy reader would get the point.

Save to `outputs/internal-threat-brief.md`. Done — that's your brief.

> **When a brief turns into a leadership question** ("are *we* exposed, and what do we do by Friday?"),
> that's a different, higher-pressure job. See [`../../UPGRADE-PATH.md`](../../UPGRADE-PATH.md).
