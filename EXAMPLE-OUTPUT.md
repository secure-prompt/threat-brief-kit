# Example Output — A Complete Threat Brief

This is the finished brief produced by running the synthetic sample report
(`_samples/synthetic/sample-threat-report.md`) through all four stages, assessed against the synthetic
organization profile (`_samples/synthetic/sample-organization-context.md`). It shows the exact shape,
length, and tone you are aiming for.

> Everything below is **synthetic** — a demonstration, not real intelligence.

---

# Threat Brief: SALTMARSH SPIDER — TIDEPOOL/BRACKISH Credential-Theft Campaign

- **Source:** Northwind Threat Labs (vendor blog), 2026-06-15 — *[synthetic sample, no link]*
- **Prepared:** 2026-06-21 | **Analyst:** R.M.

## Bottom line up front

A financially motivated actor (SALTMARSH SPIDER) is running a phishing campaign that drops a loader
(TIDEPOOL) and a credential/session stealer (BRACKISH), and has shifted toward **healthcare and finance**
targets. Because we are a healthcare organization with a large email-receiving workforce and heavy reliance
on browser-based SaaS sessions, we assess this as **High relevance**. No ransomware deployment has been
observed from this actor.

## Key findings

- The campaign begins with **spearphishing** carrying a ZIP that hides a malicious `.lnk` posing as a PDF
  invoice or benefits-enrollment document; opening it runs PowerShell to fetch the loader. *(reported as observed)*
- **TIDEPOOL** persists via a scheduled task named `MicrosoftEdgeUpdateTaskCore` and pulls down **BRACKISH**.
- **BRACKISH** steals credentials from Chromium-based browsers, crypto wallet files, and **session cookies**,
  exfiltrating over HTTPS — typically within minutes, with no lateral movement observed.
- The vendor **assesses, with moderate confidence**, that the actor is financially motivated and sometimes
  hands access to ransomware affiliates — but has **not** observed it deploying ransomware itself.
- Lures are sector-tailored: benefits/HR themes for healthcare, wire-confirmation themes for finance.

## What this means for us

**Relevance: High.** The actor is actively targeting our sector (healthcare), and its primary technique —
phishing that leads to **browser credential and session-cookie theft** — lands squarely on our biggest
exposures: a large clinical workforce that routinely receives HR/benefits email, and heavy reliance on
browser-based SaaS sessions, some not yet behind SSO/MFA. Stolen session cookies can bypass MFA on
applications that aren't protected by it.

**Most relevant TTPs for us:**
- **T1566.001 Spearphishing Attachment** + **T1204.002 User Execution** — our exposure starts here.
- **T1555.003 Credentials from Web Browsers** and **T1539 Steal Web Session Cookie** — directly threaten
  our SaaS-session-heavy environment; cookie theft is the MFA-bypass risk.
- **T1053.005 Scheduled Task** (`MicrosoftEdgeUpdateTaskCore`) — a concrete, huntable persistence artifact.

## Confidence and gaps

- **Overall confidence: Moderate**, anchored to a single (synthetic) vendor report; not independently
  corroborated here.
- The actor's motivation and ransomware-handoff behavior are the **vendor's assessment**, not confirmed fact.
- Indicators are sector-relevant but may be campaign-specific and short-lived; absence of these IOCs does
  not mean absence of the threat.

## Recommended follow-up

1. **Hunt** for the scheduled task `MicrosoftEdgeUpdateTaskCore` and for `.lnk`-spawned PowerShell across
   endpoints.
2. **Close the session-theft gap:** prioritize SSO/MFA coverage for browser-based SaaS not yet behind it,
   and review session-revocation capability for key apps.
3. **Targeted awareness** for staff likely to receive benefits/HR-themed email, ahead of any enrollment cycle.
4. **Be ready to reset credentials and invalidate sessions** for any user who executes a matching lure.

## Indicators (synthetic — do not action)

- Scheduled task: `MicrosoftEdgeUpdateTaskCore`
- Dropped file: `%APPDATA%\EdgeUpdate\edgeupd.exe`
- Domains: `tidepool-update[.]example[.]net`, `brackish-cdn[.]example[.]org`
- IPs: `198.51.100.44`, `203.0.113.92` *(RFC 5737 documentation ranges)*
- See source report for full indicator list.

---

*Produced with the Secure Prompt Workbench — Threat Brief Kit. Indicators above are synthetic and for
demonstration only.*
