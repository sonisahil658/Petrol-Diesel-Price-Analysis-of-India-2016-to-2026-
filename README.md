# Petrol-Diesel-Price-Analysis-of-India-(2016-2026)

---

## INTRODUCTION

- Fuel pricing in India is not just an economic decision — it is a combination of global crude oil markets, central government excise policy, state VAT structures, and political timing.
- India does not have truly free-market fuel pricing. Prices are officially "deregulated" but heavily influenced by government tax decisions at both central and state levels.
- Delhi is used as the **national baseline** for all fuel price benchmarking in India, as it is the capital city and the reference point for official government pricing announcements.
- This project was triggered by a real event — the **₹3/L petrol price hike in May 2026**, the first increase in 4 years — and uses that as the lens to analyse a full decade of pricing behaviour.
- The analysis covers not just what prices were, but **why they moved** — connecting every major price change to the real event that caused it.

---

## This repository consists of the following:

1. `README.md` — this file
2. `/Data` — `Petrol_Diesel_Price_Analysis.xlsx` (8 structured sheets)
3. `/Dashboard` — Screenshots of all 4 Power BI dashboard pages
4. `/Documentation` — `Project_Documentation.docx` — full methodology and source references

---

## DATA SOURCES

All data in this project is sourced from publicly available government and market records:

- **PPAC** — Petroleum Planning & Analysis Cell (Ministry of Petroleum & Natural Gas)
- **IOCL** — Indian Oil Corporation Ltd — city-wise retail price notifications
- **RBI** — Reserve Bank of India — CPI inflation and USD/INR exchange rate data
- **MoSPI** — Ministry of Statistics — CPI basket weights
- **GlobalPetrolPrices.com** — weekly international fuel price tracking
- **EIA** — US Energy Information Administration — WTI crude oil annual averages
- **ClearTax / PRS India** — state VAT tables and excise duty history

> Data compiled and verified as of May 2026.

---

## EXCEL WORKBOOK STRUCTURE (8 Sheets)

| Sheet No. | Sheet Name | Description | Data Range |
|-----------|-----------|-------------|------------|
| 1 | Yearly Trends | Annual average petrol & diesel prices — Delhi baseline | 2016–2026 |
| 2 | Monthly Prices | Month-wise petrol & diesel prices in Delhi | Jan 2016 – May 2026 |
| 3 | State-wise Prices | City/state petrol & diesel prices across 15+ cities | 2018, 2020, 2022, 2024, 2026 |
| 4 | Crude Oil Impact | WTI crude oil prices vs Indian retail fuel prices | 2016–2026 |
| 5 | Tax Breakdown | Central excise duty + state VAT components per litre | 2016–2026 |
| 6 | Inflation Relation | CPI inflation vs fuel price correlation data | 2016–2024 |
| 7 | Diesel vs Petrol | Head-to-head comparison: price, gap, usage, tax & trends | 2016–2026 |
| INDEX | Index Sheet | Full description and source credits for all sheets | — |

---

## POWER BI DASHBOARD (4 Pages)

| Page | Title | What it shows |
|------|-------|--------------|
| 1 | Overview | 10-year Delhi price trend, KPI cards, top state prices, key insights |
| 2 | State-wise | India heatmap, 15-city comparison, VAT category breakdown |
| 3 | Crude Oil Impact | WTI crude vs retail price trend, scatter plot, Retail/Crude ratio |
| 4 | Diesel vs Petrol | 10-year gap analysis, structural comparison, usage context |

📸 Screenshots of all 4 pages → `/Dashboard` folder

---

## STEP 1 : PROBLEM FRAMING

Before touching any data, four research questions were defined:

- Q1. How have petrol and diesel prices in Delhi moved over 10 years — and what events drove each major change?
- Q2. Why do petrol prices vary so significantly across Indian states for the same fuel?
- Q3. How closely do global crude oil prices actually connect to what Indians pay at the pump?
- Q4. Is there a pattern in when the government chooses to cut or raise fuel prices?

---

## STEP 2 : DATA COLLECTION

Data was collected from 7 sources across government reports, oil corporations, and market trackers.

- PPAC Annual Reports — excise duty history and policy changes
- IOCL price notifications — Delhi daily retail prices (Jan 2016 – May 2026)
- GlobalPetrolPrices.com — weekly city-wise data for state comparison
- RBI Annual Reports — USD/INR exchange rates, repo rate history
- EIA (US Energy Information Administration) — WTI crude oil annual averages
- MoSPI / ClearTax — CPI basket weights, state VAT structures
- PRS India / data.gov.in — parliamentary records on excise changes

Total data collected: **125 months** of monthly pricing, **15 cities**, **10 years** of annual data.

---

## STEP 3 : DATA CLEANING

The following transformations were performed to standardise data across sources:

- State and city name inconsistencies resolved across IOCL, PPAC, and third-party sources
- Missing monthly values filled using IOCL notification records (prices held until next revision)
- Fiscal year vs calendar year alignment — all data normalised to calendar year (Jan–Dec)
- Currency standardisation — WTI crude converted from USD/bbl to INR/bbl using RBI annual average exchange rates
- Duplicate entries removed for months where multiple price revisions occurred (only month-end price retained)
- VAT percentage formats standardised — some states report as flat rate, some as rate + cess — both converted to effective % of retail price

---

## STEP 4 : DATA MODELLING (Excel — 8 Sheets)

Each sheet was built with a specific analytical purpose:

**Sheet 1 — Yearly Trends**
Annual averages calculated from monthly data. YoY change in ₹ and % computed for both petrol and diesel. Key event column added manually from PPAC and news records.

**Sheet 2 — Monthly Prices**
125 rows of month-wise Delhi petrol and diesel prices. Petrol-Diesel Gap column calculated as:
```
Gap = Petrol Price (₹/L) − Diesel Price (₹/L)
```

**Sheet 3 — State-wise Prices**
Snapshot data for 17 cities across 5 years (2018, 2020, 2022, 2024, 2026). VAT category column added (Low / Medium / High / Very High / Highest) based on effective VAT percentage.

**Sheet 4 — Crude Oil Impact**
Retail/Crude Ratio calculated for each year to measure how much retail price diverges from crude cost:
```
Retail/Crude Ratio = Petrol Delhi (₹/L) ÷ WTI Crude ($/bbl)
```
Higher ratio = greater decoupling from global oil markets.

**Sheet 5 — Tax Breakdown**
Central excise + state VAT + dealer margin + base price for each year. Tax share % calculated:
```
Tax % of Retail = (Excise + VAT + Cess) ÷ Final Retail Price × 100
```

**Sheet 6 — Inflation Relation**
CPI annual inflation, fuel's weight in CPI basket (~7.9%), and repo rate mapped against petrol and diesel prices. Transmission channels documented.

**Sheet 7 — Diesel vs Petrol**
Price gap tracked year by year. 10-year percentage increase calculated separately for both fuels:
- Petrol: ₹64.38 → ₹97.77 = **+51.9%**
- Diesel: ₹50.19 → ₹87.62 = **+74.6%**

---

## STEP 5 : EXPLORATORY DATA ANALYSIS (EDA)

The following questions were answered through analysis:

**Q1. How did Delhi petrol prices move over 10 years?**
- Minimum: ₹64.38/L (April 2016)
- Maximum: ₹110.04/L (November 2021)
- Average: ₹85.77/L
- Total increase: ₹33.39/L (+51.9%)
- Largest single-year jump: 18.62% in 2021

**Q2. Which state charges the most and least for petrol (May 2026)?**
- Highest: Telangana/Hyderabad — ₹110.89/L (VAT: 35.2%)
- Lowest: Chandigarh — ₹94.24/L (VAT: 22.45%)
- Maximum gap between states: ₹16.65/L for the same fuel

**Q3. How closely does crude oil track retail price?**
- Crude and retail prices show 85.46% positive correlation over 10 years
- Key decoupling year: 2020 — crude fell to $20/bbl, Retail/Crude ratio hit 2.03 (highest in 10 years) due to excise hike
- Rule of thumb: ₹1/bbl crude change ≈ ₹0.50–0.65/L retail change (with full pass-through)

**Q4. Is there a pattern in when price cuts happen?**

| Year | Event | Government Action |
|------|-------|------------------|
| Oct 2018 | Pre-state election pressure | ₹1.5/L excise cut |
| Nov 2021 | UP/Punjab elections approaching | ₹5/L petrol, ₹10/L diesel cut |
| May 2022 | Inflation & election optics | ₹8/L petrol, ₹6/L diesel cut |
| Mar 2024 | General elections | ₹2/L cut |
| May 2026 | No election cycle | ₹3/L hike — first in 4 years |

---

## STEP 6 : POWER BI DASHBOARD DESIGN

- Data imported from all 7 Excel sheets into Power BI data model
- Relationships established across tables using Year and City as keys
- DAX measures created for: Avg Petrol Price, Avg Diesel Price, Fuel Gap Avg, Petrol YoY Change %, Diesel YoY Change %, Max YoY Increase, Retail/Crude Ratio, Highest/Lowest Petrol Price
- Year slicer applied across all 4 pages for interactive filtering
- India map visual used for state-wise heatmap (Page 2) and overview (Page 1)
- Scatter plot used for crude oil vs retail price correlation (Page 3)
- Dark theme applied with consistent colour coding: orange for petrol, blue for diesel

---

## KEY FINDINGS

1. **Petrol in Delhi rose 51.9% in 10 years** — from ₹64.38 in 2016 to ₹97.77 in May 2026
2. **Diesel rose faster than petrol** — 74.6% increase over the same period due to subsidy removal
3. **Tax is ~65% of retail price** — of every ₹97.77 paid, only ~₹50.72 is the actual fuel cost
4. **State inequality is significant** — Telangana residents pay ₹16.65 more per litre than Delhi residents for the same fuel
5. **Price cuts follow elections** — every major price relief from 2018 to 2024 preceded a significant election
6. **Crude oil explains only 85% of retail movement** — the remaining 15% is government tax decisions
7. **2020 was the biggest decoupling year** — crude crashed to $20/bbl, government raised excise, retail price went up

---

## DISCLAIMER

This is a research-based project created using publicly available fuel price data, government reports, and market sources. Most analysis is based on Delhi fuel price benchmarks and selected state-wise comparisons for educational and analytical purposes only.

---

## CONNECT

- LinkedIn → https://www.linkedin.com/in/sahil-soni-6b64921b4/
- Open to Data Analyst / Business Intelligence Developer roles
