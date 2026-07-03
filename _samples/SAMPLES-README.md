# Samples — Provenance and Clean-Room Statement

Every sample in this kit is **synthetic** — invented for demonstration. None of it is real threat
intelligence, and none of it comes from any employer, client, or non-public source.

## Inventory

| File | Provenance | Notes |
| --- | --- | --- |
| `synthetic/sample-threat-report.md` | Synthetic | Fictional vendor report ("Northwind Threat Labs") about a fictional actor ("SALTMARSH SPIDER"). All indicators are fabricated; IPs use RFC 5737 documentation ranges; domains use `example.*`. |
| `synthetic/sample-organization-context.md` | Synthetic | Fictional healthcare organization ("Meridian Health Partners"). Generic profile only — no real or sensitive data. |

## Why synthetic instead of a real public report

A real public report could not be redistributed inside a paid/free product without licensing concerns,
and copying real indicators risks confusion with live threat data. A synthetic report lets us ship a
complete, safe, end-to-end example that you can run immediately and that can never be mistaken for real
intelligence to act on.

## Folders

- `synthetic/` — fabricated material (this kit's samples live here).
- `public/` — reserved for clearly-attributed public source material, if added later.
- `original/` — reserved for original material authored for this kit.

## Using your own report

When you run the kit for real, use a **public** report you are allowed to use, or your own synthetic
material. Do not place internal, client, or confidential reports here or feed them to a public AI tool.
See [`../SAFETY.md`](../SAFETY.md).
