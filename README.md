# Deep Running Insights Page

This repository contains a standalone, single-file analytics page focused on long-term running performance, injury risk signals, and marathon build readiness.

Main page:
- running_deep_insights.html

Companion page:
- running_dashboard.html

## What This Page Covers

The page summarizes running history from 2021 to March 2026 and combines training metrics with narrative interpretation.

Key blocks include:
- High-level KPI strip (total runs, distance, best effort, fastest pace, marathon countdown)
- Knee injury retrospective (October 2025) with root-cause analysis and full written report
- Marathon build timeline leading to Ottawa Marathon (May 24, 2026)
- 2026 weekly load table with ACWR and HRV context
- Training status and risk/positive signal panels
- Historical trend sections:
  - Monthly volume history (2021-2026)
  - Aerobic efficiency trend (pace per heartbeat)
  - Long-run progression (all runs >= 15 km)
  - Garmin marathon prediction trend (Jan-Mar 2026)
  - Monthly run consistency heatmap-style table
  - Heart rate zone distribution vs marathon 80/20 target

## Technical Notes

- Format: static HTML + inline CSS + minimal inline JavaScript
- Dependencies: none
- Build step: none
- Interactivity: section expand/collapse toggles and report-card toggle
- Data model: values are embedded directly in the HTML (no runtime API calls)

## How To Open

Option 1:
1. Open running_deep_insights.html directly in a browser.

Option 2 (recommended during edits):
1. Start a simple local server in this folder.
2. Open the served page URL in your browser.

PowerShell example:

```powershell
py -m http.server 8000
```

## Data Sources

The analytics appear to be compiled from exports in this workspace, especially:
- Strava Data/
- Garmin Data/

The rendered page itself is currently a curated snapshot, not a live pipeline.
Raw exports are intentionally ignored by `.gitignore` in this repo.

## Updating The Page

Suggested update workflow:
1. Refresh source exports in Strava Data/ and Garmin Data/.
2. Recompute your summary metrics externally (script/notebook/manual process).
3. Update narrative text and tables in running_deep_insights.html.
4. Verify section toggles and mobile layout in a browser.
5. Commit and push to this repository.

## Publish With GitHub Pages

1. Push this repo to GitHub (for example: `running-analysis`).
2. In GitHub, open `Settings > Pages`.
3. Set source to `Deploy from a branch`, branch `main`, folder `/ (root)`.
4. Your site will publish at:
  - `https://<username>.github.io/<repo-name>/`
5. Keep `running_deep_insights.html` as a direct page URL under that site.

Optional: link this page from your main profile site homepage.

## Disclaimer

This page provides training-data interpretation and planning support. It is not medical advice or a diagnosis.
