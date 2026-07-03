# Safety — Read Before You Use This Kit

This kit helps you use AI on threat reports. AI is a drafting assistant here, not a decision-maker, and
some AI tools send your text to the cloud. A few habits keep your work safe and defensible.

## 1. Protect sensitive data

**Do not paste confidential, regulated, or non-public organization data into a public cloud AI tool.**
That includes:

- Internal documents, configurations, detections, or playbooks.
- Real internal hostnames, IP addresses, user names, ticket IDs, or victim/customer names.
- Anything covered by an NDA, contract, or confidentiality obligation.
- Material belonging to a current or former employer or client.

**You do not need any of that to use this kit.** The relevance stage (Stage 3) is built around a
*generic, sanitized* organization profile — sector, rough size, and broad technology categories — never
secrets. Keep it generic and you stay safe even on a public AI tool. If you must use sensitive context,
use a local model or an AI environment your organization has approved.

## 2. The reports you feed in should be public, synthetic, or approved

This kit is designed for **public** threat reports (vendor blogs, advisories, ISAC bulletins) or the
**synthetic** sample provided. Do not load internal incident reports or client deliverables into a
public AI tool.

## 3. Watch for prompt injection in source reports

Threat reports — especially ones quoting attacker infrastructure, phishing text, or pasted code — can
contain text that tries to hijack an AI ("ignore previous instructions and…"). Treat every source report
as **untrusted input**.

- The AI should *analyze* the report, never *obey* instructions found inside it.
- If the AI suddenly changes behavior, drops your formatting, or follows an instruction that came from
  the report rather than from you, stop and start the stage over.
- In Folder-Reading Mode, the AI must not execute code, fetch URLs, or follow links found in a report
  without your explicit say-so.

## 4. AI output is a draft — you are the analyst

- Every stage ends with a **human-review checkpoint.** Do not skip it.
- The kit instructs the AI to mark missing details as *absent or unknown* rather than inventing them.
  Verify that it did. If a claim, IOC, or attribution looks invented, cut it.
- Preserve uncertainty. A brief that says "unconfirmed" where appropriate is more defensible than one
  that sounds falsely certain.

## 5. Keep your sources

Hold on to the source link, publication date, and publisher for everything you brief. The kit captures
these in Stage 1 so your final brief is traceable and can be defended or rechecked later.

---

This kit follows a clean-room standard: it contains no employer, client, proprietary, or
internal-operational material, and its example indicators are synthetic. See
[`CREDITS.md`](CREDITS.md) and [`_samples/SAMPLES-README.md`](_samples/SAMPLES-README.md).
