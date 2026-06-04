# Labrika Onboarding Audit — Project Overview

## What This Is

A Claude/agent skill for running structured Labrika SEO audits during client onboarding. It encodes the full workflow for creating a Labrika project, running desktop and mobile audits, exporting report artifacts, and triggering targeted technical reruns after website fixes — without requiring the user to know Labrika's UI in detail.

## Use Cases

- **New client onboarding:** Add a company to Labrika, configure the project (country, region, language, search engine), run full site analysis for desktop and mobile, and hand off a clean export checklist.
- **Post-fix validation:** After a developer applies fixes, rerun only the technical audit (not the full site analysis) to verify corrections without spending unnecessary credits.
- **Export and handoff:** Inventory the exported `.xlsx`/PDF/DOCX files, cross-reference issues across reports, and produce a developer-ready issue log or handoff message.

## Skill Entry Point

Invoke via: `$labrika-onboarding-audit` in any Claude/agent session.

Default prompt:
> "Use $labrika-onboarding-audit to add a company in Labrika, run desktop and mobile audits, and guide me through saving the reports."

## Key Workflows

### Full Onboarding Audit

1. Navigate to `https://labrika.com/dashboard#/projects/new/audit`
2. Fill project fields: homepage URL, company name, country/region/language, search engine
3. Run full site analysis — both desktop and mobile
4. Wait for completion; export the full report package
5. Follow `references/report-checklist.md` for file inventory and handoff

### Technical Rerun After Fixes

1. Open the project from the Labrika dashboard
2. Use the **lower** audit-row three-dot menu (not the upper task-board menu)
3. Click `Update Analysis` → `Only Technical audit`
4. Review the confirmation screen (crawl limit, credits, project)
5. Start — confirm queue or completion

## Report Artifacts

Core exports saved under `reports/labrika/`:

| File | Purpose |
|------|---------|
| Site audit PDF / DOCX | Full report for stakeholder review |
| `4xx_errors.xlsx` | Broken pages |
| `Pages_with_broken_links.xlsx` | Internal link health |
| `Critical_markup_errors.xlsx` | HTML/schema errors |
| `Sitemap_validator.xlsx` | Sitemap coverage |
| `Images.xlsx` | Image optimization issues |
| `Thin_content_pages.xlsx` | Low-value pages |
| `Over-optimization.xlsx` | Keyword stuffing signals |
| `Essential_landing_page_elements.xlsx` | On-page completeness |
| `Site_rankings.xlsx` | Ranking snapshot (when available) |
| `Competitors_list.xlsx` / `Top_competitors.xlsx` | Competitive landscape |

## Guardrails

- Never start credit-consuming actions without user confirmation when Labrika warns about cost
- Never run Full Site Analysis when the task is only technical-fix validation
- Never invent keywords, competitors, or service area data — only use what the user provides
- Always run both desktop and mobile; a single-device audit is not considered complete

## Integration Notes

- **Browser:** Prefer the Codex in-app browser; use Chrome when login/cookies are required
- **Post-save processing:** After the user saves files, inventory the folder and offer to create a README or issue log from the artifacts
- **Cross-referencing:** Correlate broken links with 4xx errors, markup errors with affected URLs, image issues with page templates

## Repository Structure

```
SKILL.md                        — Skill definition and full workflow
agents/openai.yaml              — OpenAI agent interface config
references/report-checklist.md  — Export checklist and developer handoff template
docs/PROJECT.md                 — This file
```
