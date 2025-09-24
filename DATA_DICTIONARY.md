# Data Dictionary

Based on CMS Medicare Part D dataset structure. Column meanings inferred from names and sample data.

| Column | Meaning | Expected Type |
|--------|---------|---------------|
| Prscrbr_Geo_Lvl | Geographic level (National, State, County, etc.) | Text |
| Prscrbr_Geo_Cd | Geographic code (state abbreviation, FIPS code, or blank) | Text |
| Prscrbr_Geo_Desc | Geographic description (state name, county name, or "National") | Text |
| Brnd_Name | Brand drug name as marketed | Text |
| Gnrc_Name | Generic drug name (active ingredient) | Text |
| Tot_Prscrbrs | Total number of prescribers for this drug/geography | Integer |
| Tot_Clms | Total number of claims (prescriptions filled) | Integer |
| Tot_30day_Fills | Total 30-day equivalent fills (normalized dosage) | Decimal |
| Tot_Drug_Cst | Total drug cost in USD | Decimal |
| Tot_Benes | Total beneficiaries (unique patients) served | Integer |
| GE65_Sprsn_Flag | Suppression flag for 65+ age group | Text |
| GE65_Tot_Clms | Claims count for beneficiaries 65+ | Integer |
| GE65_Tot_30day_Fills | 30-day fills for 65+ group | Decimal |
| GE65_Tot_Drug_Cst | Drug cost for 65+ beneficiaries | Decimal |
| GE65_Bene_Sprsn_Flag | Beneficiary suppression flag for 65+ | Text |
| GE65_Tot_Benes | Total beneficiaries 65+ | Integer |
| LIS_Bene_Cst_Shr | Low Income Subsidy beneficiary cost share | Decimal |
| NonLIS_Bene_Cst_Shr | Non-LIS beneficiary cost share | Decimal |
| Opioid_Drug_Flag | Flag indicating opioid classification (Y/N) | Text |
| Opioid_LA_Drug_Flag | Long-acting opioid flag (Y/N) | Text |
| Antbtc_Drug_Flag | Flag indicating antibiotic classification (Y/N) | Text |
| Antpsyct_Drug_Flag | Flag indicating antipsychotic classification (Y/N) | Text |

## Notes
- Column definitions based on CMS Medicare Part D dataset documentation
- Suppressed values appear as `*` or `#` in numeric columns for privacy protection
- Drug flags (Opioid, Antibiotic, Antipsychotic) enable therapeutic class analysis