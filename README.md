# Pharmacy Sales Analyzer

## Executive Summary / Key Findings

### Market Overview
| Metric | 2023 Value |
|--------|------------|
| **Total Medicare Part D Spending** | **$551.11 Billion** |
| **Average Cost per Claim** | $170.42 |
| **Average Cost per Beneficiary** | $566.98 |

**Data source:** [CMS Medicare Part D — Prescribers by Geography and Drug (2023)](https://www.cms.gov/Research-Statistics-Data-and-Systems/Statistics-Trends-and-Reports/Medicare-Provider-Charge-Data/Part-D-Prescriber)

### Top Performance
| Category | Leader | Value |
|----------|--------|-------|
| **Highest Cost Drug** | Eliquis | $37B |

### Geographic Distribution
| Rank | State | Total Spending |
|------|-------|---------------|
| 1 | California | $27B |
| 2 | New York | $22B |
| 3 | Florida | $20B |

## The Charts

### Full Dashboard Export (PDF)
**[View Complete Dashboard - pharmacy_sales_analyzer_visuals.pdf](powerbi/pharmacy_sales_analyzer_visuals.pdf)**
*Two-page comprehensive dashboard export showing all key metrics and visualizations.*

---

### Top 10 Medicare Drugs by Total Spending (2023)
![Top 10 Medicare Drugs by Total Spending](powerbi/top10_drugs.png)<br>
*Top 10 Medicare Drugs by Total Spending (2023).*

### Top 10 States by Medicare Drug Spending (2023)
![Top 10 States by Medicare Drug Spending](powerbi/top10_states.png)<br>
*Top 10 States by Medicare Drug Spending (2023).*

### Medicare Drug Spending by State (2023)
<img src="powerbi/map_state_spend.png?v=2" alt="Medicare Drug Spending by State" width="600"><br>
*Medicare Drug Spending by State (2023).*

### Cost per Beneficiary by State (2023)
<img src="powerbi/top_beneficiary_cost.png" alt="Cost per Beneficiary by State" width="600"><br>
*Cost per Beneficiary by State (2023).*

## Decisions This Enables
- Target education/outreach for the highest-cost drugs.
- Allocate resources to states with disproportionate spending.
- Evaluate brand vs generic substitution opportunities.
- Flag unusually high-cost patterns for fraud or outlier review.

## What's Inside
- `data/medicare_part_d_sales_2023.csv` — CMS Medicare Part D prescriber data (115,936 rows)
- `powerbi/pharmacy_sales_analyzer.pbix` — Power BI Desktop file with data model and visuals
- `powerbi/pharmacy_sales_analyzer_visuals.pdf` — Two-page PDF export of the dashboard

## How to View / Reproduce
1. **Power BI Desktop:** Open `powerbi/pharmacy_sales_analyzer.pbix`
2. Go to **Transform Data** to review cleaning steps
3. **Refresh** data to confirm calculations
4. **Explore:** Review DAX measures and data model relationships

## Metrics Used
See detailed definitions and DAX formulas in [`powerbi/POWERBI_MEASURES.md`](powerbi/POWERBI_MEASURES.md)

Key metrics:
- Total Spending, Total Claims, Beneficiaries
- Cost per Claim, Cost per Beneficiary
- Top N rankings by geography and drug type

## Data Dictionary & Cleaning
- **Column definitions:** [`DATA_DICTIONARY.md`](DATA_DICTIONARY.md)
- **Cleaning policy:** [`CLEANING.md`](CLEANING.md)
- **QA checks:** Row count validation, null handling for suppressed values

## Limitations & Next Steps
- Medicare Part D only (excludes other insurance types).
- 2023 snapshot only (no trends).
- Suppressed values (`*`, `#`) treated as missing.
- Not adjusted for inflation or population.
- Next Steps: Add multi-year data, normalize by state population, publish live dashboard.

---

## Contact
**Victor Ruiz** | Data Analyst
odinruiz52@yahoo.com | [LinkedIn](https://linkedin.com/in/victor-ruiz-analyst)
