# Data Dictionary

**Dataset:** SDSS DR17 Stellar Classification (`data/raw/star_classification.csv`)
**Size:** 100,000 rows x 18 columns

## Original columns

| Column | Type | Meaning | Units / categories | Expected missing values |
|---|---|---|---|---|
| obj_ID | text | Photometric object identifier. **Not unique** in this file: values were rounded in the source, so different objects share IDs | ID | None |
| alpha | float | Right ascension: the object's east-west position on the sky | degrees, 0 to 360 | None |
| delta | float | Declination: the object's north-south position on the sky | degrees, -90 to 90 (this data: about -19 to 83) | None |
| u | float | Brightness through the ultraviolet filter | magnitude (lower = brighter) | -9999 means no measurement (1 row) |
| g | float | Brightness through the green filter | magnitude | -9999 means no measurement (1 row) |
| r | float | Brightness through the red filter | magnitude | -9999 means no measurement (0 rows) |
| i | float | Brightness through the near-infrared filter | magnitude | -9999 means no measurement (0 rows) |
| z | float | Brightness through the infrared filter | magnitude | -9999 means no measurement (1 row) |
| run_ID | int | Imaging run that photographed the object | ID | None |
| rerun_ID | int | Version of the image processing | always 301 | None |
| cam_col | int | Camera column (1 of 6) that took the image | 1 to 6 | None |
| field_ID | int | Field (section of the run) the object is in | ID | None |
| spec_obj_ID | text | Spectroscopic observation identifier. **Unique for every row**, used as the key | ID | None |
| class | text | Object type | GALAXY, STAR, QSO (quasar) | None |
| redshift | float | How much the object's light is stretched by its motion away from us; a measure of distance | unitless; stars about 0, quasars up to 7.01 | None |
| plate | int | Spectroscopic plate used for the observation | ID | None |
| MJD | int | Date of the spectroscopic observation | Modified Julian Date (days since 17 Nov 1858); 2000-03-05 to 2020-03-24 | None |
| fiber_ID | int | Optical fibre that collected the object's light | 1 to 1000 | None |

## Columns added during cleaning (Week 3)

| Column | Type | Meaning |
|---|---|---|
| obs_date | date | `MJD` converted to a calendar date |
| obs_year | int | Year of `obs_date` |
| obs_month | int | Month of `obs_date` |
| ra_band | text | `alpha` grouped into 60-degree bands (0-60 ... 300-360) |
| hemisphere | text | North if `delta` >= 0, otherwise South |
| obj_ID_shared | bool | True if the row's `obj_ID` also appears in another row |
| negative_redshift | bool | True if redshift < 0 |
| suspicious_galaxy_z | bool | True for galaxies with redshift < 0 |
| qso_high_z_check | bool | True for quasars with redshift > 6 (probably fitting errors) |
| redshift_outlier | bool | Redshift outside 1.5 x IQR for its class |
| r_outlier | bool | r magnitude outside 1.5 x IQR for its class |
