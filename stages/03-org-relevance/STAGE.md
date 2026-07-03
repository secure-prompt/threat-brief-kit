---
id: "03-org-relevance"
title: "Organization Relevance"
contract_version: "stage-contract-v1"
owner: "human"
purpose: "Assess what the report means for your organization using generic, sanitized context — never sensitive data."
entry_criteria:
  - "Stage 2 output.md exists with verified extraction."
required_inputs:
  - path: "input-template.md"
    type: "template"
  - path: "../../_templates/organization-context-template.md"
    type: "template"
  - path: "../02-structured-extraction/output.md"
    type: "prior-stage-output"
allowed_context:
  - "Stage 2 extraction"
  - "A GENERIC, sanitized organization profile (sector, rough size, broad platform categories)"
ai_task: "Reason about relevance and exposure from the generic profile. Flag the most relevant TTPs and likely impact. Never request or use sensitive/internal data."
human_review_gate: "Analyst confirms the relevance assessment is reasonable AND that no sensitive organization data was introduced."
outputs:
  - path: "output.md"
    type: "markdown"
output_paths:
  - "stages/03-org-relevance/output.md"
completion_criteria:
  - "A 'what this means for us' assessment exists with a clear relevance level (High/Medium/Low) and rationale."
  - "The most relevant TTPs/exposures are identified."
  - "No confidential or internal-specific data was used."
failure_modes:
  - "Coaxing the user to paste internal hostnames, account names, tooling specifics, or secrets."
  - "Overstating relevance to seem useful, or understating it to seem safe."
handoff:
  next_stage: "stages/04-internal-brief"
mutation_rules:
  read_only:
    - "STAGE.md"
    - "input-template.md"
    - "../02-structured-extraction/output.md"
  writable:
    - "output.md"
    - "notes.md"
---

# Stage 3 — Organization Relevance

**Goal:** answer the question every reader actually has — *does this matter to us?* — using only a
**generic, sanitized** picture of your organization. This is the stage that turns a summary into
intelligence.

> **Safety first (this is the one stage where it really matters).** Use only broad categories: your
> sector, rough size, and general platform types (e.g. "Windows endpoints, M365, browser-based SaaS").
> **Do not** enter internal hostnames, IP addresses, account names, specific product/tool names, ticket
> data, or anything non-public — especially in a cloud AI tool. You do not need any of that for a useful
> relevance call. See [`../../SAFETY.md`](../../SAFETY.md).

## What to do

1. If you don't have one yet, fill in `_templates/organization-context-template.md` once — keep it
   generic — and reuse it for every future report. (A synthetic example is in
   `_samples/synthetic/sample-organization-context.md`.)
2. Run the prompt below with your Stage 2 extraction and your generic profile.
3. Review for both **soundness** and **safety** before continuing.

## Prompt to paste into your AI

```
You are a CTI analyst assessing whether a threat report is relevant to a specific organization.

You will receive:
1. A structured extraction of a threat report.
2. A GENERIC, sanitized organization profile (sector, rough size, broad platform categories, general exposures).

Produce a "What this means for us" assessment:
- Overall relevance: High / Medium / Low, with a one-paragraph rationale grounded in the profile.
- Why it is / isn't relevant: connect the actor's targeting, sectors, and TTPs to the profile.
- Most relevant TTPs for this organization (the few that matter most here, and why).
- Plausible impact if this threat reached this organization (general terms).
- 2–4 recommended follow-up actions appropriate to the profile (hunting, control checks, awareness).

Rules:
- Use ONLY the generic profile provided. Do NOT ask for, or assume, internal hostnames, IPs, account
  names, specific tool/vendor names, or any confidential data.
- Be honest about relevance. Do not inflate it to seem useful or deflate it to seem cautious.
- Keep recommendations realistic for an organization of this size and capability.

Then stop and wait for my review.

Threat extraction:
[PASTE STAGE 2 OUTPUT]

Generic organization profile:
[PASTE YOUR SANITIZED PROFILE]
```

## Human review checkpoint — do not skip

- [ ] The relevance level (High/Medium/Low) is **honest** and the rationale is grounded in the profile.
- [ ] The "most relevant TTPs" actually map to how this organization operates.
- [ ] Recommendations are realistic for this size/capability — not a generic wishlist.
- [ ] **No sensitive or internal-specific data** entered the workspace or the AI prompt.

Save to `output.md`, then continue to [`../04-internal-brief/STAGE.md`](../04-internal-brief/STAGE.md).
