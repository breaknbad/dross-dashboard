# EV History Dashboard

## Overview
Admin dashboard for Break'n Bad IR pack EV tracking data. Displays current EV ratios, trends, and historical statistics.

## Files
- `ev-history.html` - Main dashboard (self-contained HTML)
- `ev-data.json` - Generated data file from SQLite database
- `README.md` - This file

## Data Export
The dashboard uses data exported from `~/clawd/data/ir-ev-tracking.db` via:

```bash
cd ~/clawd
node scripts/ir-export-ev-data.js
```

This script:
- Exports last 48h of snapshots to `ev-data.json`
- Calculates 24h movers
- Generates time series data for charts
- Creates historical statistics

## Dashboard Sections
1. **Dashboard Overview** - Total packs, +EV counts, averages
2. **Current Snapshot** - All packs sorted by EV ratio
3. **EV Trend Charts** - Line charts for top packs over time
4. **Biggest Movers** - Packs with largest 24h EV changes
5. **Historical Statistics** - Data coverage and averages

## Deployment
Deployed to GitHub Pages at: https://breaknbad.github.io/dross-dashboard/ev-history.html

To update:
1. Run export script: `node scripts/ir-export-ev-data.js`
2. Commit and push: `git add -A && git commit -m "Update EV data" && git push`

## Features
- Mobile responsive
- BnB branding (dark theme, orange/gold accents)
- Color-coded EV ratios (red/green/gold)
- Auto-refresh every 5 minutes
- Chart.js for interactive charts
- Self-contained (no external dependencies except Chart.js CDN)