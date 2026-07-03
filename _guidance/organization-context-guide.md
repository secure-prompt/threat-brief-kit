# Guide — Building a Safe, Useful Organization Profile

Stage 3 turns a generic summary into intelligence by asking "does this matter to *us*?" The quality of
that answer depends on a profile that is **useful but generic.**

## The balance

- **Useful enough** that relevance reasoning has something to grip: your sector, rough size, the broad
  platform categories you run, and your general exposures.
- **Generic enough** that pasting it into a cloud AI tool is harmless: no internal names, addresses,
  tool/vendor specifics, account names, ticket data, or secrets.

If you can imagine the profile appearing in a public conference talk about your sector without anyone
wincing, it's at the right altitude.

## What actually drives relevance

For most threat reports, the relevance call hinges on a few generic facts:

- **Sector** — many actors target specific industries. Sector match is often the biggest signal.
- **Platform categories** — does the threat hit Windows? Browser sessions? M365? Linux? Cloud IaaS?
- **Exposure shape** — large email-receiving workforce? Heavy SaaS/session reliance? Internet-facing services?
- **Capability** — your rough ability to detect/respond shapes which follow-ups are realistic.

None of those require a single secret.

## Write it once, reuse it forever

Fill `_templates/organization-context-template.md` a single time and reuse it for every report. Revisit it
a couple of times a year, or when something big changes (a migration, a merger, a new platform).

## Example

`_samples/synthetic/sample-organization-context.md` shows a complete, safe, generic profile for a
fictional healthcare organization.
