# Labrika Report Checklist

Use this reference when exporting or handing off Labrika audit artifacts after a new-company audit.

## Completion Checks

- Main report URL exists, usually `https://labrika.com/dashboard#/site/<site-id>/report/main_report`.
- Audit status is complete, or Labrika clearly says it is still queued/running.
- Desktop audit was run or explicitly queued.
- Mobile audit was run or explicitly queued.
- Whole-site/full-audit scope was selected.
- Any skipped inputs are documented, especially missing keywords, competitors, or region.

For post-fix technical reruns:

- Labrika was opened from My Projects or the project dashboard.
- The lower audit-row three-dot menu was used, not the upper task-board/project menu.
- The action `Update Analysis` was used.
- `Only Technical audit` was selected in the `Start report` modal.
- The confirmation screen was reviewed for selected pages/crawl limit and remaining credits.
- The rerun was started, queued, or the blocking error was captured.

## Files To Export Or Request

Ask the user to save the full audit package into the project. For this repo's convention, use `reports/labrika/`, or a dated/company subfolder when running multiple companies.

Core report files:

- Site audit report PDF.
- Site audit report DOCX, if available.
- `4xx_errors.xlsx`.
- `Pages_with_broken_links.xlsx`.
- `Critical_markup_errors.xlsx`.
- `Sitemap_validator.xlsx`.
- `Images.xlsx`.
- `External_files.xlsx`.
- `External_links.xlsx`.
- `Thin_content_pages.xlsx`.
- `Over-optimization.xlsx`.
- `Essential_landing_page_elements.xlsx`.

Ranking and competitive files, when available:

- `Site_rankings.xlsx`.
- `Competitors_list.xlsx`.
- `Top_competitors.xlsx`.
- `Exclusion_of_competitors.xlsx`.

Include any additional Labrika exports that are visible for the project, especially mobile-specific files if Labrika separates them.

## Post-Save Processing

After the user saves the files into the project:

1. Inventory the folder with `find <folder> -maxdepth 1 -type f | sort`.
2. Create or update a short `README.md` explaining each file and when to use it.
3. Create an issue log if requested. Use spreadsheet parsing for `.xlsx` instead of manual text guessing.
4. Cross-reference issues across files:
   - Broken links with 4xx errors.
   - Critical markup errors with affected page URLs.
   - Image issues with page templates and image inventory.
   - Sitemap issues with canonical/indexability findings.
   - Thin content with landing page and ranking reports.
5. Separate confirmed website issues from Labrika false positives or items needing manual verification.

## Developer Handoff Shape

When asked for a message to a developer lead, include:

- Project/report URL.
- Folder path containing saved reports.
- Executive summary with counts.
- Critical issues first.
- Links or local file paths for every report used.
- Clear notes on what has already been fixed versus what remains.
- Any manual verification needed, such as false-positive 404 checks.
