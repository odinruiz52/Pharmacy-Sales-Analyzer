# Power BI Measures & Visual Logic

## Core Measures (DAX Formulas)

### Primary Metrics
```dax
Total Spending = SUM(TableName[Tot_Drug_Cst])
```
Total cost across all drugs in the current filter context.

```dax
Total Claims = SUM(TableName[Tot_Clms])
```
Total number of prescriptions filled.

```dax
Beneficiaries = SUM(TableName[Tot_Benes])
```
Total unique patients served.

### Calculated Ratios
```dax
Cost per Claim = DIVIDE([Total Spending], [Total Claims])
```
Average cost per prescription filled.

```dax
Cost per Beneficiary = DIVIDE([Total Spending], [Beneficiaries])
```
Average spending per patient.

## Visual Logic & Interactions

### Top N Drugs Chart
- **Ranking:** Order drugs by `[Total Spending]` descending
- **Display:** Top 10 drugs with cost labels
- **Slicers:** Allow filtering by:
  - Geographic level (National, State, County)
  - Brand vs Generic (using Brand_Name vs Gnrc_Name)
  - Therapeutic class (Opioid, Antibiotic, Antipsychotic flags)

### Geographic Analysis
- **Map Visual:** State-level spending using `Prscrbr_Geo_Desc` where `Prscrbr_Geo_Lvl = "State"`
- **Bar Chart:** Top states by total spending
- **Drill-down:** Enable drilling from state to county level (if county data present)

### Therapeutic Class Breakdown
- **Clustered Bar:** Compare spending across drug classifications
- **Filters:** Separate analysis for Opioid vs Non-Opioid, Antibiotic usage patterns

## **TODO:** Additional Measures to Build
- Spending growth (if multi-year data added)
- Market share percentages by drug/manufacturer
- Geographic spending per capita (requires population data join)