# Start Here — Threat Brief Kit

Welcome. This kit turns a public threat report into a clean, sourced, one-page internal brief —
using the AI you already have. You do the judging; the AI does the drafting. It takes about
20–30 minutes the first time, less after that.

**You will move through four stages:**

1. **Report Intake** — capture what the report is and where it came from.
2. **Structured Extraction** — pull out claims, actors, malware, IOCs, TTPs, and ATT&CK mappings.
3. **Organization Relevance** — decide what it means for your organization (safely).
4. **Internal Brief** — produce the final one-page brief.

You review and approve the output at the end of every stage. Nothing moves forward on autopilot.

---

## First: read the safety note (2 minutes)

Open **[`SAFETY.md`](SAFETY.md)** before you start. The one rule that matters most:
**do not paste confidential employer, client, or regulated data into a public AI tool.** Stage 3
is built to assess relevance using *generic, sanitized* context so you never have to. The kit will
remind you again when it matters.

---

## Then: pick how you will run it

This kit works with whatever AI you already use. Choose the mode that fits your tool.

### Mode A — Chat Mode (ChatGPT, Claude, Gemini, a local model, any chat AI)

You copy and paste. For each stage:

1. Open the stage folder (start with `stages/01-report-intake/`).
2. Open `STAGE.md` and copy everything under the heading **"Prompt to paste into your AI."**
3. Paste it into your AI chat.
4. Paste the inputs it asks for (the report text, or your filled template).
5. Read what the AI produces. **Check it against the stage's review checklist.**
6. Save the result into that stage's `output.md` (create the file).
7. Move to the next stage and repeat.

You never need a folder-reading tool. Chat Mode does the whole workflow.

### Mode B — Folder-Reading Mode (Claude Code, Cursor, or similar agentic tools)

The AI reads the folder for you. To start:

1. Open this kit's folder as your project/workspace in the tool.
2. Paste this instruction:

   > Read `workbench.yml`, then `stages/01-report-intake/STAGE.md`. Follow that stage's contract.
   > Only write to the files its `mutation_rules` allow. Stop at the human-review gate and wait for me.

3. Review and approve at each gate. The agent advances stage by stage, writing each `output.md` for you.

Folder-Reading Mode is faster (less copy/paste). It is **not** required and gives the same result as Chat Mode.

---

## What you need before you begin

- A **public** threat report you want to brief (vendor blog, ISAC bulletin, advisory). A ready-to-try
  synthetic example lives in `_samples/synthetic/sample-threat-report.md` if you just want to see how it works.
- About 20–30 minutes.
- Your AI tool of choice.

## See what "done" looks like first (recommended)

Open **[`WHAT-YOU-WILL-CREATE.md`](WHAT-YOU-WILL-CREATE.md)** and **[`EXAMPLE-OUTPUT.md`](EXAMPLE-OUTPUT.md)**.
`EXAMPLE-OUTPUT.md` is a complete brief produced from the synthetic sample report — it shows the exact
quality and shape you are aiming for.

When you are ready, open `stages/01-report-intake/STAGE.md` and begin.
