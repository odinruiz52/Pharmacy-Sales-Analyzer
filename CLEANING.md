# Data Cleaning Policy

## Core Rule
**Treat `*` and `#` in numeric columns as missing/null values, NOT as zero.**

CMS suppresses values for privacy when counts are too low. Converting these to zero would artificially inflate volume metrics and skew cost calculations.

## Target Columns for Cleaning
Focus on these key numeric fields:
- `Tot_Drug_Cst` — Total drug cost (primary metric)
- `Tot_Clms` — Total claims count
- `Tot_Benes` — Total beneficiaries
- `Tot_30day_Fills` — 30-day equivalent fills
- `Tot_Prscrbrs` — Total prescribers

## Power Query Steps
1. **Import CSV** with proper text encoding and delimiter detection
2. **For each numeric column:**
   - Transform → Replace Values: `"*"` → `null`
   - Transform → Replace Values: `"#"` → `null`
   - Change Data Type → Decimal Number (for costs) or Whole Number (for counts)
3. **Validate results** using QA checks below

## QA Checks to Run
- **Row count:** Should equal ~115,936 records after import
- **No negative costs:** `Tot_Drug_Cst` should have no values < 0
- **Null count tracking:** Document how many values became null after suppression replacement
- **Data type confirmation:** All target columns show as numeric (not text) in Power Query

## Notes
- Keep the original CSV file unchanged in `data/` folder
- Perform all cleaning in Power Query (not in source file)
- If high null percentages impact key metrics, document in README.md Executive Summary