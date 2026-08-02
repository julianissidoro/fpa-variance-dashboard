# FP&A Executive Dashboard — LATAM 2024-2025

Interactive FP&A executive dashboard analyzing budget variance, YoY growth 
and monthly trends across 2 regions and 5 LATAM countries. Built with Power BI.

![Dashboard Preview](Captura%20de%20pantalla%202026-08-02%20201634.png)

## Business Context

Multi-country finance operations require consolidated visibility for executive 
decision-making. This dashboard enables real-time analysis of budget execution, 
YoY performance and country-level variance — designed for CFO-level reporting.

## Dataset

- **Source**: Google BigQuery export (CSV)
- **Coverage**: 5 countries, 4 departments, 24 months (2024–2025), Actual vs Budget
- **Tables**: expenses (960 rows), departments (20 rows)

## Dashboard Components

| Visual | Description |
|---|---|
| KPI Cards | Total Actual, Total Budget, Variance %, YoY Growth |
| Bar Chart | Budget Variance % by Country |
| Line Chart | Monthly Actual Spend: 2024 vs 2025 |
| Summary Table | Country-level Actual, Budget, YoY abs, execution tracker |
| Slicers | Filter by Year, Country and Quarter |

## DAX Measures

- `Total_Actual` / `Total_Budget` — filtered aggregations with CALCULATE
- `Variance_pct` — DIVIDE for safe division
- `YoY_Growth` — year-over-year % growth
- `Total_Actual_PY` — prior year comparison with DATEADD
- `LATAM_SUR_ACTUAL` — region-locked measure with REMOVEFILTERS
- `perc_exp` — country share of total with ALL context override
- `tracker` — conditional label with IF()

## Tech Stack

- Power BI Desktop
- DAX (Data Analysis Expressions)
- Power Query (M language)
- GitHub for version control
