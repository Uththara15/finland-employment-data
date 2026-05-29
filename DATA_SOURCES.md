# Data Sources

Full provenance for every figure used in the dashboard.

---

## Statistics Finland Labour Force Survey (LFS)

**URL:** https://stat.fi/en/statistics/tyti
**Licence:** CC BY 4.0

Series used: annual unemployment rate 15-74, employment rate 20-64, unemployment by sex.

Key anchors:

| Year | Unemployment 15-74 | Employment 20-64 | Published |
|------|-------------------|-----------------|-----------|
| 2024 | 8.4% | 76.7% | Statistics Finland LFS 2024 annual |
| 2025 | 9.7% | 76.0% | Statistics Finland LFS 2025, Jan 27 2026 |

2025 release confirms: 278,000 unemployed persons (39,000 more than 2024). Male rate 10.2%, female rate 9.1%.

Direct link to 2025 release: https://stat.fi/en/publication/cmfpdadi40gsg07un1urfrm3q

StatFin database table: https://pxdata.stat.fi/PXWeb/pxweb/en/StatFin/StatFin__tyti/statfin_tyti_pxt_13aj.px

---

## OECD Labour Force Statistics via FRED

**URL:** https://fred.stlouisfed.org
**Licence:** Open, free to use with attribution

| FRED series ID | Description | Last value used |
|----------------|-------------|-----------------|
| LRHUADTTFIA156S | Unemployment rate 25+, annual | 8.1% in 2025 |
| SLUEM1524ZSFIN | Youth unemployment rate 15-24, annual | 21.5% in 2025 |

---

## World Bank World Development Indicators

**URL:** https://data.worldbank.org
**Licence:** CC BY 4.0

SLUEM1524ZSFIN (youth unemployment 15-24): 21.5% in 2025, updated February 2026.

---

## Eurostat Regional Labour Market Statistics

**URL:** https://ec.europa.eu/eurostat/databrowser/view/lfst_r_lfu3rt
**Licence:** Free reuse with attribution

Series: lfst_r_lfu3rt — Unemployment rates by NUTS2 region, age 15+.

2023 regional values confirmed from Eurostat and EURES Finland Labour Market Information report (December 2024). 2024 and 2025 regional values estimated proportionally from the confirmed national change (+1.3 pp in 2025) applied to each region using the 2023 ratios.

Uusimaa 2023: 7.6% — confirmed via EURES Finland report.

---

## European Commission Spring 2026 Forecast

**URL:** https://economy-finance.ec.europa.eu/economic-surveillance-eu-member-states/country-pages/finland/economic-forecast-finland_en

Used for: 2026 unemployment forecast 10.1%, 2027 forecast 9.8%, employment growth projections.

---

## EURES / European Labour Authority

**URL:** https://eures.europa.eu/living-and-working/labour-market-information/labour-market-information-finland_en

Used for: shortage occupation classifications, sector employment share data, regional labour market context.

---

## April 2026 Monthly Data

**URL:** https://stat.fi/en/publication/cmfp8krfh9xpz08urq66cuzar

April 2026 monthly release: 11.6% unemployment rate (non-seasonally adjusted), highest since May 2015. 336,000 unemployed persons. Youth rate 28.0%.

---

## How to access raw data yourself

**Statistics Finland PXWeb API**

Base: `https://pxdata.stat.fi/PXWeb/api/v1/en/StatFin/`

Documentation: https://pxdata.stat.fi/api1.html

Fetch table metadata:
```
GET https://pxdata.stat.fi/PXWeb/api/v1/en/StatFin/tyti/statfin_tyti_pxt_13aj.px
```

Then POST a JSON query to get data in JSON, CSV or XLSX.

**Eurostat API**

```
GET https://ec.europa.eu/eurostat/api/dissemination/statistics/1.0/data/lfst_r_lfu3rt?geo=FI1B&time=2023
```

**FRED API**

```
GET https://api.stlouisfed.org/fred/series/observations?series_id=SLUEM1524ZSFIN&api_key=YOUR_KEY&file_type=json
```
