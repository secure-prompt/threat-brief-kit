# Threat Brief: SALTMARSH SPIDER — TIDEPOOL/BRACKISH Credential-Theft Campaign

> **This is the worked sample output**, produced from the synthetic sample report. When you run the kit on
> your own report, your finished brief replaces this file. Everything below is synthetic — a demonstration,
> not real intelligence. (See `EXAMPLE-OUTPUT.md` for the same brief with commentary.)

- **Source:** Northwind Threat Labs (vendor blog), 2026-06-15 — *[synthetic sample, no link]*
- **Prepared:** 2026-06-21 | **Analyst:** R.M.

## Bottom line up front

A financially motivated actor (SALTMARSH SPIDER) is running a phishing campaign that drops a loader
(TIDEPOOL) and a credential/session stealer (BRACKISH), and has shifted toward **healthcare and finance**
targets. As a healthcare organization with a large email-receiving workforce and heavy reliance on
browser-based SaaS sessions, we assess this as **High relevance**. No ransomware deployment has been
observed from this actor.

## Key findings

- Phishing ZIP hides a malicious `.lnk` posing as a PDF invoice / benefits document; opening it runs
  PowerShell to fetch the loader. *(reported as observed)*
- **TIDEPOOL** persists via scheduled task `MicrosoftEdgeUpdateTaskCore` and pulls down **BRACKISH**.
- **BRACKISH** steals browser credentials, crypto wallet files, and **session cookies** over HTTPS, usually
  within minutes; no lateral movement observed.
- The vendor **assesses, with moderate confidence**, financial motivation and occasional access handoff to
  ransomware affiliates; **no** direct ransomware deployment observed.

## What this means for us

**Relevance: High.** The actor targets our sector and its core technique — phishing into **browser
credential and session-cookie theft** — hits our biggest exposures: a large clinical workforce receiving
HR/benefits email, and heavy browser-based SaaS session use, some not yet behind SSO/MFA. Stolen session
cookies can bypass MFA where it isn't enforced.

**Most relevant TTPs:** T1566.001 (Spearphishing Attachment), T1204.002 (User Execution),
T1555.003 (Credentials from Web Browsers), T1539 (Steal Web Session Cookie), T1053.005 (Scheduled Task).

## Confidence and gaps

- **Overall confidence: Moderate** — single (synthetic) vendor source, not independently corroborated.
- Motivation and ransomware-handoff are the vendor's **assessment**, not confirmed fact.
- Absence of these indicators does not rule out the threat.

## Recommended follow-up

1. Hunt for scheduled task `MicrosoftEdgeUpdateTaskCore` and `.lnk`-spawned PowerShell.
2. Prioritize SSO/MFA for browser-based SaaS not yet covered; review session-revocation capability.
3. Targeted awareness for staff receiving benefits/HR email ahead of enrollment cycles.
4. Be ready to reset credentials and invalidate sessions for any user who executes a matching lure.

## Indicators (synthetic — do not action)

- Scheduled task: `MicrosoftEdgeUpdateTaskCore` | Dropped file: `%APPDATA%\EdgeUpdate\edgeupd.exe`
- Domains: `tidepool-update[.]example[.]net`, `brackish-cdn[.]example[.]org`
- IPs: `198.51.100.44`, `203.0.113.92` *(RFC 5737)* — See source report for full list.
