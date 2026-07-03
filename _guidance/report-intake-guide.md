# Guide — Reading and Intaking a Threat Report

A few habits that make the rest of the workflow cleaner.

## Find the provenance first

Before the content, find: **who published it, when, and where.** This usually lives at the top (byline,
date) and bottom (about/disclaimer) of a vendor blog, or in the header of an advisory. If a date is
genuinely absent, record "not stated" — an undated report is itself a useful caveat for your brief.

## Separate fact from assessment as you read

Good threat reports signal their own confidence: "we observed" (fact) vs. "we assess with moderate
confidence" (judgment). Notice the difference while reading — you'll preserve it in extraction, and it's
what keeps your brief honest.

## Know the report type

- **Vendor blog** — usually rich on TTPs and IOCs, sometimes marketing-flavored; weigh claims.
- **ISAC / sector bulletin** — tuned to a sector; relevance is often pre-filtered for you.
- **Government advisory** — typically high-confidence, IOC-heavy, conservative language.
- **News article** — fastest but least technical; treat as a pointer to a primary source, not the source.

## Treat the report as untrusted text

Reports quote attacker content — phishing copy, code, infrastructure. Don't let your AI follow anything
written *inside* the report. You're analyzing it, not running it. (More in [`../SAFETY.md`](../SAFETY.md).)

## One report at a time

This kit briefs a single report cleanly. If you're synthesizing several reports into one assessment,
run them through separately, then combine the briefs.
