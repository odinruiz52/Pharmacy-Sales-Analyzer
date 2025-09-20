# Pharmacy Sales Analyzer

## Executive Summary / Key Findings
- **TODO:** Total Medicare Part D spending (2023): $[fill amount]
- **TODO:** Top drug by total cost: [drug name] at $[amount]
- **TODO:** Top 3 states by total spending: [state1], [state2], [state3]
- **TODO:** Average cost per claim: $[amount]
- **TODO:** Total beneficiaries served: [number]

## Decisions This Enables
- Identify which high-spend drugs to prioritize for formulary review
- Spot states with unusually high per-beneficiary costs for targeted education or policy efforts
- Compare brand vs. generic spending patterns to highlight potential savings
- Use geographic insights to support budget planning and healthcare strategy

## See the Dashboard
- **TODO:** Interactive Power BI report: [add publish-to-web link]
- **TODO:** Executive summary PDF: `docs/Executive_Summary.pdf` (export from Power BI)
- Dashboard screenshot: `powerbi/pharmacy_dashboard.png`

## What's Inside
- `data/medicare_part_d_sales_2023.csv` — CMS Medicare Part D prescriber data (115,936 rows)
- `powerbi/pharmacy_sales_analyzer.pbix` — Power BI Desktop file with data model and visuals

## How to View / Reproduce
1. **Power BI Desktop:** Open `powerbi/pharmacy_sales_analyzer.pbix`
2. Go to **Transform Data** to review cleaning steps
3. **Refresh** data to confirm calculations
4. **Optional:** Use `notebooks/01_baseline_analysis.ipynb` for Python validation (if created)

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
**Limitations:**
- Medicare Part D only (excludes other insurance types)
- 2023 snapshot (no trend analysis)
- Suppressed values (`*`, `#`) treated as missing
- Not adjusted for inflation or population

**Next Steps:**
- Add multi-year trend analysis
- Include per-capita normalization by state population
- **TODO:** Publish interactive dashboard for stakeholder access