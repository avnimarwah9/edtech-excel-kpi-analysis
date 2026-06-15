# EdTech India - Excel KPI Analysis (Practice Project)

A formula-based Excel analytics project using a synthetic dataset of 2,500+ student enrollments across 15 Indian EdTech companies, built to practice real-world Excel skills used in data analyst roles: data cleaning, calculated columns, and KPI summary tables driven entirely by formulas (no manual entry).

## About this project

This is a **learning/practice project**. The dataset is synthetically generated to reflect realistic patterns in the Indian EdTech market (pricing in INR, GST slabs, city-tier distribution, course categories, completion and refund rates). It is not sourced from Kaggle or any external dataset provider.

I built and worked through this project to practice formula-based analysis end-to-end — from raw, messy data to a clean KPI dashboard, and to understand exactly how each formula works so I can apply the same logic to real datasets.

## What’s in the workbook

|Sheet                   |Purpose                                                                         |
|------------------------|--------------------------------------------------------------------------------|
|`RAW DATA - DO NOT EDIT`|Original, unmodified dataset (2,509 rows) — kept as a reference copy            |
|`Working Data`          |Cleaned copy with additional calculated columns                                 |
|`Lookup Tables`         |City → Tier/Regional Head mapping, GST rate reference                           |
|`KPI Summary`           |Formula-driven summary tables (no pivot tables) by Course Category and City Tier|
|`Project Notes`         |Documentation of cleaning steps, formulas used, and findings                    |

## Data cleaning steps

- Removed duplicate `Enrollment_ID` rows (8 duplicates found and removed)
- Removed empty trailing rows
- Standardized city and company names using `TRIM(PROPER())` to fix inconsistent casing and trailing spaces

## Calculated columns (Working Data)

- **Cleaned_City / Cleaned_Company** — `TRIM(PROPER())` for consistent formatting
- **Discount_Category** — nested `IF` to bucket discounts into No Discount / Low / Medium / High
- **Profit_Flag** — `IF` flag for Loss Making / Low Margin / Healthy Margin based on gross margin %
- **Month_Year, Year, Quarter** — extracted from text dates using `DATE`, `TEXT`, `VALUE`, `CHOOSE`, and `ROUNDUP`

## KPI Summary formulas

Built using `COUNTIFS`, `SUMIFS`, `AVERAGEIFS`, and `IFERROR` (to handle divide-by-zero cases), cross-tabulating:

- Total enrollments, net revenue, and gross profit by **Course Category** and **City Tier**
- Average margin %, completion rate, refund rate, and average student rating per segment

## Key findings

- Coding & Tech has the highest gross margin (~58.9%) and completion rate (~66.3%) among all course categories
- K-12 Academics has the lowest completion rate (~60.1%), though margins are broadly similar (54–59%) across categories
- Tier 2 and Tier 3 cities show 6–8% lower completion rates than Tier 1, despite comparable refund rates, suggesting access/infrastructure factors rather than dissatisfaction

## Tools used

Microsoft Excel (formulas: `COUNTIFS`, `SUMIFS`, `AVERAGEIFS`, `IFERROR`, `IF`, nested `IF`, `TRIM`, `PROPER`, `TEXT`, `DATE`, `CHOOSE`, `ROUNDUP`)

## Files

- `EdTech_India_Portfolio_Dataset.xlsx` : full workbook with raw data, cleaned data, lookup tables, and KPI summary
