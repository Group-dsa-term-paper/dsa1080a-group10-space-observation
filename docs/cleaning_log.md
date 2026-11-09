# Cleaning Log

Input: `data/raw/star_classification.csv` (100,000 rows x 18 columns)
Output: `data/processed/star_classification_clean.csv` (99,999 rows x 28 columns)
Code: `notebooks/03_cleaning_analysis.ipynb`

The raw file is never modified; all steps run on a copy.

| Step | Issue found | Rows/values affected | Decision | Reason |
|---|---|---|---|---|
| 1 | -9999 placeholder in `u`, `g`, `z` | 3 values, all in 1 row (a star) | Convert to missing, then drop the row | -9999 means "no measurement". The row is missing 3 of 5 bands, so filling would invent most of its data. Losing 1 of 100,000 rows has no real effect. |
| 2 | `rerun_ID` is 301 in every row | 1 column | Drop the column | A constant carries no information. |
| 3 | `obj_ID` repeats (19,154 repeats) but rows are different objects | 33,183 rows share an ID | Keep all rows, flag with `obj_ID_shared`, use `spec_obj_ID` as the key | IDs were rounded in the source file. `spec_obj_ID` is unique and there are no fully duplicated rows, so nothing should be removed. |
| 4 | Category text could be inconsistent | 0 values changed | Strip spaces and upper-case `class` | Safeguard; the three labels were already clean. |
| 5 | Dates stored as MJD numbers | All rows | Add `obs_date`, `obs_year`, `obs_month`; keep `MJD` | Needed for time comparisons. No dates failed to parse. |
| 6 | Sky positions are continuous | All rows | Add `ra_band` and `hemisphere` | Lets us compare regions of the sky. |
| 7 | Negative redshift | 13,724 rows (13,682 stars, 42 galaxies) | Keep, flag with `negative_redshift` and `suspicious_galaxy_z` | Small negative values are real for stars moving towards us; galaxies are unexpected. |
| 8 | Quasar redshift above 6, bunched near 7.01 | 118 quasars | Keep, flag with `qso_high_z_check` | Quasars this distant are extremely rare; the values look like the limit of the fitting software. Medians are used in the analysis so they have little effect. |
| 9 | Statistical outliers in redshift and r band | 2,614 rows | Keep, flag with `redshift_outlier` and `r_outlier` | Outliers are judged within each class, since the classes naturally differ. Flagging keeps the evidence without deleting real objects. |

## Before / after

| Measure | Before | After |
|---|---|---|
| Rows | 100,000 | 99,999 |
| Columns | 18 | 28 |
| Null values (incl. -9999) | 3 | 0 |
| Fully duplicated rows | 0 | 0 |
| Class labels changed | - | 0 |
| Columns dropped | - | 1 |
| Columns added | - | 11 |
| Rows flagged as outliers | - | 2,614 |
| Quasars flagged for high redshift | - | 118 |

Rows retained: 99.999%. The cleaned dataset still meets the 15,000 rows x 10 columns minimum.
