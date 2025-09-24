# Power BI Measures & Visual Logic

This project uses the CMS Medicare Part D 2023 dataset loaded as **'medicare_part_d_sales_2023 (2)'**.

## Core Measures (DAX)

### Primary Totals
```dax
Total Spending =
SUM('medicare_part_d_sales_2023 (2)'[Tot_Drug_Cst])
```

```dax
Total Claims =
SUM('medicare_part_d_sales_2023 (2)'[Tot_Clms])
```

```dax
Beneficiaries =
SUM('medicare_part_d_sales_2023 (2)'[Tot_Benes])
```

### Normalized Metrics
```dax
Cost per Claim =
DIVIDE([Total Spending], [Total Claims], BLANK())
```

```dax
Cost per Beneficiary =
DIVIDE([Total Spending], [Beneficiaries], BLANK())
```

### Context / Share
```dax
% of Total Spending =
VAR AllScopeTotal =
    CALCULATE([Total Spending], ALL('medicare_part_d_sales_2023 (2)'))
RETURN DIVIDE([Total Spending], AllScopeTotal, BLANK())
```

**Tip:** Use `% of Total Spending` in tooltips or on bar labels to show contribution.

## Visual Logic & Interactions

### Executive Summary (Page 1)

**Cards:** Total Spending, Total Claims, Cost per Claim, Cost per Beneficiary

**Top 10 Drugs (bar):**
- **Axis:** Brnd_Name
- **Value:** Total Spending
- **Filter:** Top N = 10 by [Total Spending]
- **Sort:** Descending by [Total Spending]
- **Optional:** add `% of Total Spending` as a data label or tooltip

**Top 10 States (bar):**
- **Axis:** Prscrbr_Geo_Desc (State)
- **Value:** Total Spending
- **Filter:** Top N = 10 by [Total Spending]
- **Slicer:** Prscrbr_Geo_Desc (State dropdown)

### Geographic Spending (Page 2)

**Filled Map:**
- **Location:** Prscrbr_Geo_Desc (State)
- **Value:** Total Spending

**Bar – Cost per Beneficiary by State:**
- **Axis:** Prscrbr_Geo_Desc
- **Value:** Cost per Beneficiary
- **Sort:** Descending by Cost per Beneficiary

## Formatting Guidelines

**In the model, set formats:**
- **Total Spending:** Currency, display units Auto (or Billions)
- **Total Claims/Beneficiaries:** Whole number (display units Millions if large)
- **Per-metrics:** Currency, 2 decimals

## Column Reference
Confirmed columns from 'medicare_part_d_sales_2023 (2)':
- `Tot_Drug_Cst` — Total drug cost in USD
- `Tot_Clms` — Total claims count
- `Tot_Benes` — Total beneficiaries served
- `Brnd_Name` — Brand drug name
- `Gnrc_Name` — Generic drug name
- `Prscrbr_Geo_Desc` — Geographic description (state name)
- `Prscrbr_Geo_Lvl` — Geographic level (National, State, etc.)
- `Opioid_Drug_Flag` — Opioid classification flag (Y/N)
- `Antbtc_Drug_Flag` — Antibiotic classification flag (Y/N)
- `Antpsyct_Drug_Flag` — Antipsychotic classification flag (Y/N)