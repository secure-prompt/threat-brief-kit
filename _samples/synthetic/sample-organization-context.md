# Sample Organization Context (Synthetic)

> **SYNTHETIC SAMPLE.** "Meridian Health Partners" is a fictional organization invented for this
> example. It contains no real or sensitive data. Use it to see how Stage 3 (Organization Relevance)
> works, then build your own from `_templates/organization-context-template.md` — kept generic.

## Organization profile

- **Name (for your eyes only — not needed by the AI):** Meridian Health Partners
- **Sector / industry:** Healthcare — regional hospital and outpatient network
- **Approximate size:** ~3,000 employees, ~12 sites
- **Geography:** North America
- **Primary platforms (broad categories):** Windows endpoints, Microsoft 365, Chromium-based browsers,
  several cloud SaaS applications for scheduling and billing
- **Identity:** Cloud identity provider with SSO; MFA enabled for most but not all applications
- **Security capability:** Small internal SOC; EDR deployed on most endpoints; email filtering in place
- **Crown jewels (general):** Patient records, billing systems, staff email and SaaS sessions

## Known exposures / watch items (general, non-sensitive)

- Large, distributed clinical workforce that frequently receives benefits- and HR-themed email
- Heavy reliance on browser-based SaaS sessions (scheduling, billing, records portals)
- Not all SaaS applications are behind SSO/MFA yet

> Note how everything above is **generic**: sector, rough size, broad platform categories, and general
> exposures. No internal hostnames, IPs, account names, tooling specifics, or secrets. That is exactly
> what keeps this safe to use with a cloud AI tool.
