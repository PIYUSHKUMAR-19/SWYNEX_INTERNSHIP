# Chess Game Exploratory Data Analysis (EDA) — Microsoft Excel

![Microsoft Excel](https://img.shields.io/badge/Tool-Microsoft%20Excel-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white)
![Project Type](https://img.shields.io/badge/Project-Exploratory%20Data%20Analysis-2463EB?style=for-the-badge)
![Dataset](https://img.shields.io/badge/Game%20Records-19%2C524-6D28D9?style=for-the-badge)

## Overview

This project explores a chess-game dataset using **Microsoft Excel**. The objective is to turn raw game records into useful, understandable insights about game outcomes, player-rating differences, recorded game length, opening popularity, and game volume over time.

The workbook combines data-quality checks, formula-based helper fields, PivotTables, PivotCharts, KPI cards, and a dashboard. The analysis is exploratory: it identifies patterns and relationships in the observed records, rather than proving cause and effect.

> **Project focus:** Data quality first, meaningful analysis second, and clear communication through a dashboard.

## Project Objectives

- Understand the dataset's structure and completeness.
- Identify missing values, suspicious ratings, questionable timestamps, and unusual move counts.
- Compare White and Black outcomes and explore rating advantage.
- Examine outcome patterns across recorded move-count groups.
- Identify frequently occurring chess openings.
- Explore monthly game-record volume.
- Summarize the results in an Excel dashboard and a written findings register.

## Tools and Excel Techniques

- **Microsoft Excel** — analysis and reporting
- **Excel Tables** — structured data and helper columns
- **Excel formulas** — `IF`, `AND`, `OR`, `COUNT`, `COUNTIF`, `COUNTIFS`, `COUNTBLANK`, `SUM`, `AVERAGE`, `MEDIAN`, `YEAR`, `MONTH`, and date formatting
- **PivotTables** — summarizing outcomes and categories
- **PivotCharts** — comparing distributions and trends
- **Data-quality checks** — missing values, invalid categories, rating-range checks, timestamp checks, and move-count checks
- **Dashboard design** — KPI cards, chart titles, consistent layout, and explanatory findings

## Workbook Contents

| Worksheet | Purpose |
|---|---|
| `CHESS_UPDATED` | Source/reference worksheet containing the original and earlier cleaned fields |
| `EDA_Base` | Working analysis table with selected source fields and derived helper columns |
| `Data_Quality` | Counts and percentages for key data-quality issues |
| `EDA_Analysis` | Summary KPIs and calculations used to understand the dataset |
| `Pivot_Rating_Outcome` | Outcomes grouped by rating-advantage category |
| `Pivot_Move_Outcome` | Outcomes grouped by recorded move-count category |
| `Pivot_Opening` | Most frequently occurring opening labels |
| `Pivot_Monthly_Games` | Number of dated game records by month |
| `Pivot_EndReason` | Distribution of reported game termination reasons |
| `EDA_CHART` | Dashboard with six KPI cards and five charts |
| `KEY_FINDINGS` | Written summary of the main observations and limitations |

*Worksheet names may be case-insensitive in Excel. If your local workbook uses a slightly different name, use the equivalent worksheet.*

## Dashboard Features

The dashboard brings together six headline metrics and five visual analyses.

### KPI Cards

- Total game records
- Rated-game share among records with a known rated status
- White wins
- Black wins
- Draws
- Median recorded move count

### Charts

1. **Game outcomes by rating advantage** — compares the outcome distribution for games where White or Black had a higher validated rating.
2. **Game outcomes by recorded move count** — compares results across move-count ranges.
3. **Top 10 most frequent chess openings** — ranks opening labels by number of records.
4. **Monthly chess game volume** — shows the monthly distribution of records with valid creation timestamps.
5. **Game termination reasons** — summarizes the reported reason a game ended.

## Selected Findings

The following figures are from the workbook analysis and should be rechecked if the source data, formulas, or PivotTable filters change.

### 1. Game outcomes

The workbook contains **19,524 game records**:

| Recorded outcome | Games | Share of all records |
|---|---:|---:|
| White wins | 9,617 | 49.26% |
| Black wins | 8,787 | 45.01% |
| Draws | 901 | 4.61% |
| Unknown/other outcomes | 219 | 1.12% |

Among the **18,404 decisive games** (White or Black wins), White accounts for approximately **52.25%** of wins and Black for **47.75%**. This describes the dataset and does not prove that playing White causes a higher win rate.

### 2. Rating advantage and wins

For games where one player had a validated rating advantage of at least 200 points, the higher-rated side won **4,579 of 5,768 decisive games (about 79.39%)**. This suggests an association between a larger rating advantage and winning. It is not a causal conclusion, and the result depends on the rating-validation rules used in this project.

### 3. Recorded game length and draws

The draw share was approximately **2%** in the 41–60 recorded-move group and about **23%** in the 151–349 group. The longest group is much smaller than the middle groups, so its percentage should be interpreted alongside its sample size. The move-count field is derived from move notation and does not necessarily represent full numbered turns.

### 4. Opening variety

The ten most frequent opening labels account for approximately **2,535 games (12.98% of the dataset)**. This indicates that the records are spread across many opening categories rather than being dominated by a single label. Opening names with inconsistent capitalization or whitespace should be standardized before making definitive rankings.

### 5. Monthly record volume

**August 2017** contains **5,411 records**, compared with 1,637 in July 2017 and 1,423 in September 2017. August represents approximately 27.85% of the 19,426 records with valid creation timestamps. This unusual concentration may reflect a collection or sampling effect; the dataset alone cannot establish a real-world increase in chess activity.

### 6. Termination reasons

The current termination-reason summary reports resignation as the most frequent category, followed by checkmate. Unknown termination reasons remain visible in the analysis rather than being silently assigned to a known category.

## Data Quality and Validation

The project includes checks for the following issues:

- **Game IDs:** 396 records contain the placeholder `NOT_AVAILABLE`; some other ID values appear more than once. Repeated IDs are reviewed separately from exact duplicate records.
- **Rated status:** 95 records have an unknown or misspelled status.
- **Creation timestamps:** 98 records have no usable creation timestamp.
- **Last-move timestamps:** 109 records have a missing last-move timestamp.
- **Move counts:** four values were flagged for review: one zero, one negative value, and two values above 349.
- **Ratings:** negative, very low, and above-range raw ratings are flagged. New analysis-ready rating fields use a working range of **100–3,500** and are derived from the raw values, rather than converting negative ratings to positive values.
- **Unavailable rating differences:** 521 games could not be assigned to a valid rating-advantage group and should be excluded from that comparison only—not removed from the full dataset.

The 100–3,500 rating range is a **project-specific screening rule**, not a universal maximum for every chess rating system. Values outside it are treated as requiring review, not automatically proven false.

## Limitations and Interpretation Notes

- The analysis is descriptive and observational; associations do not establish causation.
- Missing values and unknown categories can affect percentages and comparisons.
- A spike in monthly volume may be due to how records were collected or sampled.
- Opening names may contain capitalization and whitespace inconsistencies.
- Move counts extracted from notation may not be equivalent to full numbered turns.
- Rating-based findings depend on the selected validation rules and on the availability of both players' ratings.
- A complete final reconciliation of every dashboard KPI against every PivotTable is a recommended follow-up before using the figures for formal reporting. Refreshing PivotTables or changing filters can change chart totals.

## How to Explore the Workbook

1. Start with `EDA_CHART` for the headline metrics and visual summary.
2. Read `KEY_FINDINGS` for the interpretations and cautions.
3. Use `Data_Quality` to understand data limitations.
4. Open the relevant PivotTable worksheet to inspect the counts behind each chart.
5. Use `EDA_Base` to trace each analytical field back to its source or helper formula.

## Suggested Repository Structure

```text
chess-eda-excel/
├── README.md
├── Chess_EDA_Final.xlsx
└── screenshots/
    └── chess_eda_dashboard.png
```

Use your actual workbook filename if it differs from `Chess_EDA_Final.xlsx`. For a stronger GitHub presentation, add a screenshot of the final `EDA_CHART` sheet at `screenshots/chess_eda_dashboard.png`. Avoid including personal data or unrelated worksheets in the screenshot.

## Conclusion

This project demonstrates an Excel-based EDA workflow: inspecting data quality, engineering analytical fields, summarizing records with PivotTables, visualizing patterns with PivotCharts, and communicating findings through a dashboard. The main value of the project is not just the charts—it is the process of making the data more interpretable while clearly documenting uncertainty and limitations.

---

**Created by:** Piyush Kumar  
**Project:** Chess Game Exploratory Data Analysis using Microsoft Excel
