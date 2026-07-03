# Northwind Threat Labs — Threat Intelligence Report

> **SYNTHETIC SAMPLE — NOT A REAL REPORT.** "Northwind Threat Labs," the actor "SALTMARSH SPIDER,"
> the malware families, and all indicators below are invented for demonstration. Indicators use
> documentation-only ranges (RFC 5737 IPs, example domains) and fabricated hashes. Do not block,
> hunt, or escalate on anything in this file. See `_samples/SAMPLES-README.md`.

**Report title:** SALTMARSH SPIDER Expands TIDEPOOL Loader Campaign Against Healthcare and Finance
**Publisher:** Northwind Threat Labs (fictional)
**Publication date:** 2026-06-15
**Report type:** Vendor threat intelligence blog
**TLP:** CLEAR (synthetic)

---

## Summary

Since April 2026, Northwind Threat Labs has tracked an expanding campaign by the financially motivated
actor we track as **SALTMARSH SPIDER**. The group delivers a lightweight loader, **TIDEPOOL**, which
in turn deploys the **BRACKISH** information stealer. Recent activity shows a marked shift toward
healthcare providers and regional financial institutions in North America and Western Europe, a change
from the group's earlier, opportunistic targeting.

We assess with **moderate confidence** that SALTMARSH SPIDER is financially motivated and operates as an
access-and-theft crew, occasionally handing off access to ransomware affiliates. We have **not** observed
SALTMARSH SPIDER deploying ransomware directly.

## Initial access

Campaigns begin with **spearphishing emails** carrying a ZIP attachment. The ZIP contains a malicious
Windows shortcut (`.lnk`) disguised as a PDF invoice or a benefits-enrollment document. When opened, the
shortcut launches PowerShell to retrieve and run the TIDEPOOL loader.

Lure themes observed:

- "Updated benefits enrollment — action required" (healthcare targets)
- "Q2 wire confirmation" (finance targets)

## Execution and behavior

1. The `.lnk` invokes `powershell.exe` with an encoded command that downloads TIDEPOOL from an
   attacker-controlled host.
2. TIDEPOOL establishes persistence via a Scheduled Task named `MicrosoftEdgeUpdateTaskCore`.
3. TIDEPOOL beacons to its command-and-control server and pulls down the BRACKISH stealer.
4. BRACKISH harvests credentials from Chromium-based browsers, cryptocurrency wallet files, and saved
   session cookies, then exfiltrates them over HTTPS to the C2.

BRACKISH makes no attempt at lateral movement in the activity we observed; it is focused on rapid
credential and session theft, typically completing within minutes of execution.

## Indicators of compromise (synthetic)

**File hashes (SHA-256):**

- `a1b2c3d4e5f6000000000000000000000000000000000000000000000000abcd` — TIDEPOOL loader
- `f6e5d4c3b2a1000000000000000000000000000000000000000000000000dcba` — BRACKISH stealer

**Network:**

- `tidepool-update[.]example[.]net` — TIDEPOOL staging host
- `brackish-cdn[.]example[.]org` — BRACKISH C2
- `198.51.100.44` — C2 IP (RFC 5737 documentation range)
- `203.0.113.92` — staging IP (RFC 5737 documentation range)

**Host:**

- Scheduled Task: `MicrosoftEdgeUpdateTaskCore`
- Dropped file: `%APPDATA%\EdgeUpdate\edgeupd.exe`

## MITRE ATT&CK techniques

- T1566.001 — Phishing: Spearphishing Attachment
- T1204.002 — User Execution: Malicious File
- T1059.001 — Command and Scripting Interpreter: PowerShell
- T1053.005 — Scheduled Task/Job: Scheduled Task
- T1555.003 — Credentials from Password Stores: Credentials from Web Browsers
- T1539 — Steal Web Session Cookie
- T1041 — Exfiltration Over C2 Channel

## Recommended mitigations

- Block execution of `.lnk` files delivered from email and the internet where feasible.
- Restrict or monitor PowerShell execution; enable script block logging.
- Alert on creation of scheduled tasks impersonating browser/OS updaters.
- Reset credentials and invalidate sessions for any user who executed the lure.
- Hunt for the indicators above (note: synthetic in this sample).

## Assessment

Northwind Threat Labs assesses with **moderate confidence** that SALTMARSH SPIDER will continue to focus
on healthcare and finance through 2026, given the group's apparent success monetizing stolen credentials
and session tokens. Organizations in these sectors with credential-heavy SaaS footprints are most at risk.
