# Finland Labour Market Tracker

An interactive multi-tab analytics dashboard covering Finnish unemployment rates, employment by industry and regional trends from 2015 through 2025, with April 2026 monthly context.

Built entirely in vanilla HTML, CSS and JavaScript. No framework, no build step, no backend. Open the file in a browser and it works.

Live demo: https://uththara15.github.io/finland-employment-data/

---

## What it shows

**Overview tab**
- National unemployment trend 2015-2025 split by total, youth (15-24) and adult (25+)
- Employment share by sector (donut chart)
- Youth vs adult grouped bar chart
- Finland vs EU27 employment rate comparison
- Key readings panel with documented findings

**Regions tab**
- Heatmap of 8 Finnish regions across 11 years — hover any cell for the exact figure
- Per-region sparklines showing full trajectory at a glance
- 2025 ranking bar chart from lowest to highest unemployment

**Industry tab**
- Stacked employment chart by sector 2015-2023
- Horizontal bar of 2025 unemployment rate per sector, colour coded by severity
- Shortage occupation panel (red, amber, green severity)

**Trends tab**
- Finland vs EU27 annual comparison line chart
- Percentage-point change per region from 2019 to 2025
- Six structural context cards covering the construction collapse, ICT resilience, April 2026 monthly reading and the EC 2026-2027 forecast

**Controls**
- Year-from filter (2015, 2017, 2019, 2021)
- Metric toggle: unemployment rate / employment rate
- Four-tab navigation, all charts update live

---

## Data sources

| Source | Series | Coverage |
|--------|--------|----------|
| Statistics Finland Labour Force Survey | Unemployment rate 15-74, employment rate 20-64 | 2015-2025 annual |
| OECD via FRED (LRHUADTTFIA156S) | Adult 25+ unemployment rate | 2015-2025 annual |
| World Bank WDI via FRED (SLUEM1524ZSFIN) | Youth unemployment rate 15-24 | 2015-2025 annual |
| Eurostat lfst_r_lfu3rt | Regional unemployment by NUTS2 | 2015-2023 confirmed |
| European Commission Spring Forecast 2026 | Unemployment outlook 2026-2027 | Forecast |
| EURES / European Labour Authority | Shortage occupations | 2024-2025 |

All sources are open access under CC BY 4.0 or equivalent open licences.

**Primary data anchor:** Statistics Finland LFS annual release published 27 January 2026 confirms 9.7% national unemployment rate in 2025, 278,000 unemployed persons, employment rate 76.0% for age 20-64.

Regional values for 2024 and 2025 are estimated by proportional scaling from the confirmed national figures using the regional ratios established in the last available Eurostat NUTS2 release. They are directionally accurate but not directly quoted official figures for those years.

---

## Tech stack

| Layer | Choice | Reason |
|-------|--------|--------|
| Language | Vanilla HTML, CSS, JavaScript | Zero build step, runs anywhere, easy to share as a single file |
| Charts | Chart.js 4.4.1 via CDN | Responsive, accessible, no framework dependency |
| Hosting | GitHub Pages | Free static hosting, one-click from repo settings |

---

## Running locally

No installation needed.

```bash
git clone https://github.com/Uththara15/finland-jobs-tracker.git
cd finland-jobs-tracker
open finland_jobs_tracker.html
```

Or serve with Python if you prefer a local server:

```bash
python -m http.server 8000
# open http://localhost:8000/finland_jobs_tracker.html
```

---

## Deploying to GitHub Pages

1. Push this repo to GitHub
2. Go to Settings > Pages
3. Source: Deploy from a branch
4. Branch: main, folder: / (root)
5. Save

The dashboard will be live at `https://yourusername.github.io/finland-jobs-tracker/finland_jobs_tracker.html`

---

## Design decisions

**Single-file architecture.** HTML, CSS, JavaScript and data all live in one file. Send one file, open in browser, done. No build tools, no Node, no dependencies to install.

**Data embedded rather than fetched live.** The Statistics Finland PXWeb API and Eurostat REST API were used during development to verify figures. Values are then embedded directly in the JavaScript. The dashboard loads instantly, works offline and does not break if an upstream API changes its schema.

**Real numbers, not synthetic.** Every figure is anchored to a published official release. Where exact regional breakdowns for 2024-2025 are not yet available at NUTS2 level, values are proportionally scaled from the confirmed national figure rather than invented.

---

## Author

Madee Uththara Deegoda Gamage
Bachelor of Engineering in ICT, Data Analytics and AI
JAMK University of Applied Sciences, Finland

GitHub: https://github.com/Uththara15
LinkedIn: https://linkedin.com/in/uththara15

---

## Licence

Code: MIT — see `LICENSE`
Data: Original data from Statistics Finland (CC BY 4.0), OECD, Eurostat, World Bank. Attribution required when reusing source data.
