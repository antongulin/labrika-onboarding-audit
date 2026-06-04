---
name: labrika-onboarding-audit
description: Run a new-company onboarding workflow in Labrika for full SEO audits and rerun technical audits after fixes. Use when the user asks to add a company or website to Labrika, create a Labrika project, run desktop and mobile audits, collect SEO/technical audit data, export Labrika report files, guide manual saving of Labrika audit artifacts, or update/rerun Labrika analysis after website fixes.
---

# Labrika Onboarding Audit

## Overview

Use this skill to create a new Labrika project for a company website, run a full site audit for desktop and mobile, and hand the user a clean checklist for saving the exported audit files into their project.

Prefer the Codex in-app browser for Labrika when the user already has it open. Use Chrome when login, cookies, or profile-specific access are required. Do not change billing, delete projects, alter account settings, or spend unexpected credits without confirming with the user.

For post-fix validation, use the rerun workflow to update only the technical audit instead of starting a full site analysis or rankings-only report.

## Quick Start

1. Open Labrika:
   - New audit page: `https://labrika.com/dashboard#/projects/new/audit`
   - Help center: `https://labrika.com/help`
2. Confirm or collect the required company inputs:
   - Website homepage URL.
   - Company/project name.
   - Target country, region/city, and language.
   - Search engine if the field is present.
   - Keywords and competitors, only if the user provides them.
3. Create the project and choose the full site audit option.
4. Run the audit for desktop and mobile.
5. Wait for the report to finish. A completed audit commonly lands on a URL like `https://labrika.com/dashboard#/site/<site-id>/report/main_report`.
6. Export the full report package and guide the user to save it in the project.

If the UI differs from these instructions, inspect visible labels and use Labrika Help before guessing.

## Field Rules

- **Website/domain**: Enter the canonical homepage URL for the company. Keep the protocol if Labrika accepts it. Use the root homepage unless the user specifically asks to audit a subdirectory.
- **Project name**: Use the business name when known, otherwise use the domain.
- **Country/region/language**: Ask the user if not clear. For local businesses, use the service market, not the agent's location.
- **Search engine**: Use the user's target market. For US local SEO, prefer Google US when available.
- **Device/crawler mode**: Run both desktop and mobile. If Labrika requires separate runs or projects, keep names distinguishable, such as `<Company> - Desktop` and `<Company> - Mobile`.
- **Scope/crawl limit**: Choose full website or all available pages. Do not intentionally cap the crawl unless the user asks.
- **Sitemap/robots options**: Include sitemap discovery when available. Do not override robots or crawler restrictions unless the user explicitly approves.
- **Keywords**: Add/import only user-provided keywords. Do not invent keywords for the setup step.
- **Competitors**: Add only user-provided competitors. If none are provided, leave competitors empty and rely on Labrika's discovered competitor reports after the audit.

## Audit Workflow

1. Check login state. If Labrika asks for authentication, ask the user to log in or switch to the authenticated browser.
2. Open the new project audit route.
3. Fill the project fields using the Field Rules above.
4. Before starting the audit, summarize the visible configuration in one short message and call out any unknowns.
5. Start the audit.
6. Monitor progress until the main report is available or Labrika clearly says the audit is queued.
7. If Labrika offers separate desktop/mobile controls, repeat the run for the missing device mode.
8. When complete, open the main report and relevant side reports.
9. Use `references/report-checklist.md` for exports and handoff.

## Rerun Technical Audit After Fixes

Use this workflow when the user says the website fixes are done and wants Labrika to recheck the technical audit.

1. Open Labrika projects. If needed, use the home/projects page from the dashboard and select the SEO area.
2. Find the matching project by company name or domain.
3. Open the lower audit-row three-dot menu next to the audit metrics/critical errors area.
   - Do not use the upper three-dot/task-board menu near `+ Create a task board`; that menu contains project/task-board actions like rename, inactive, and delete.
4. Click `Update Analysis`.
5. In the `Start report` modal, choose `Only Technical audit`.
   - Do not choose `Full Site Analysis` unless the user asks for all reports again.
   - Do not choose `Only search rankings` for technical-fix validation.
   - Do not choose `AI Visibility Audit` unless the user asks for AI visibility.
6. On the `Start Technical Site Audit` confirmation screen, check:
   - selected pages or crawl limit,
   - credits/pages left,
   - project name/domain if visible.
7. If the confirmation implies unexpected cost, too few credits, a wrong project, or an unexpectedly large crawl, stop and ask the user.
8. Click `Start`.
9. Confirm whether Labrika started the technical audit, queued it, or showed an error.
10. After the rerun finishes, ask the user to save the refreshed technical audit exports and then use `references/report-checklist.md` for post-save processing.

## Export And Handoff

Read `references/report-checklist.md` before exporting or telling the user what to save.

Minimum handoff:

- Confirm the Labrika project/report URL.
- Confirm desktop and mobile coverage, or explain what is still queued.
- List files the user should save.
- Tell the user where to put files if they have a project convention, for example `reports/labrika/`.
- After the user saves files, offer to create a README, issue log, or developer handoff from the artifacts.

## Guardrails

- Do not guess business facts, service areas, keywords, competitors, or campaign goals.
- Do not start paid or credit-consuming actions when Labrika warns about cost or quota without user confirmation.
- Do not delete old projects or overwrite existing project settings.
- Do not treat a single device audit as complete when the user asked for desktop and mobile.
- Do not claim the audit is complete until Labrika shows a finished report or the exported files exist.
- Do not rerun full analysis or rankings when the task is only to verify technical fixes.
