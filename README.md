# Beyond the Seed

By Jake Logsdon. A report and browser-calculated dashboard for Financial Data Analytics II.

Question: How did Final Four appearance rates differ between teams seeded 1–4 and teams seeded 5–16 in the men's NCAA tournaments from 2015–2025, and which lower-seeded programs broke through?

Reader: a college basketball analyst preparing a March Madness preview.

Rows: one team selected for one tournament, including First Four participants. Period: 2015–2025, excluding canceled 2020.

## Files
- `index.html`: report, findings, charts, source, and metric definitions.
- `dashboard.html`: year and team controls, four metrics, three charts, selected-entry table.
- `styles.css`: shared responsive design.
- `app.js`: CSV loading, filtering, metric calculation, and SVG charts. No chart library or build step.
- `march_madness_2015_2025.csv`: the 680-row analysis file used by both pages and intended for Tableau.
- `README.md`: this documentation.

## Data and preparation
Source: Nishaan Amin, March Madness Data, https://www.kaggle.com/datasets/nishaanamin/march-madness-data . Input file: `KenPom Barttorvik.csv` in the user-supplied archive. Kaggle lists the dataset license as CC0: Public Domain (verified through the public dataset metadata on October 25, 2026).

Keep YEAR 2015 through 2025; source contains no 2020 tournament. Keep TEAM, CONF, SEED, ROUND. Rename these Season, Team, Conference, Seed, Finish_Round. Add Seed_Group (Seeds 1-4 or Seeds 5-16) and Final_Four (1 for Finish_Round 1, 2, or 4; otherwise 0). No joins, imputations, or outcome corrections. Exclude other years and unused columns. Source team labels are retained. ROUND 68 identifies First Four eliminations; do not mistake it for a win count. Do not use W as NCAA tournament wins; it is a season statistic.

Checks: 68 entries per year, 217 distinct teams, no duplicate Season/Team pair, no missing retained fields, four Final Four teams per year. These are internal checks, not independent verification of every result.

## Four summary metrics
At defaults: Tournament entries = 680; Final Four appearances = 40; Final Four rate: seeds 1–4 = 29/160 = 18.13%; Final Four rate: seeds 5–16 = 11/520 = 2.12%. Each rate's denominator is selected entries within its own seed group, including First Four entrants. Round only for display. If no entries exist, show N/A. All dashboard metrics and charts use the same filtered rows.

## Preview and publish
Serve this folder with a static HTTP server. Do not open HTML directly: browser CSV fetch requires HTTP. For GitHub Pages, put these files at the repository root and publish the root of the main branch using Settings > Pages. Links are relative so a repository subpath works. Internet fonts are optional; system fallbacks are supplied. CSV and chart calculations have no external dependency.

## Remaining project work
Publish on GitHub Pages and check logged-out access. Build and publish Tableau yourself from this exact CSV. After verifying default filters and all four actual Tableau results, add the agreement table and Tableau URL to the report; do not invent a link or claim agreement before verification. Submit the required four-line text file only after both dashboards are live.

