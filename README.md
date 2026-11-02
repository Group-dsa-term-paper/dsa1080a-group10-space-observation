# DSA 1080A — Group 10: Space Observation and Satellite Data Trends

**Course:** DSA 1080A, Programming for Data Science — Future Data Lab (Five-week group project)
**Group:** 10
**Project option:** 10 — Space Observation and Satellite Data Trends
**Dataset:** SDSS DR17 stellar classification data (stars / galaxies / quasars)


## Project description

We are using the SDSS DR17 (Sloan Digital Sky Survey) stellar classification
dataset to describe what the sample contains and how stars, galaxies and
quasars differ in distance, brightness and sky position, as a base for
automated sky-survey summaries.

**Target users:**
- Astronomy students and educators
- Amateur astronomers and citizen scientists
- Survey planners (deciding where to point telescopes next)

**Overall objective:** Describe what the SDSS DR17 sample contains and how
stars, galaxies and quasars differ in distance, brightness and sky position,
as a base for automated sky-survey summaries.

**Specific objectives:**
1. Profile and validate the dataset's quality.
2. Compare the three object classes by redshift and brightness.
3. Examine when and where in the sky the observations were made.

**Draft research questions:**
1. What share of the sample is each class? (category-share chart)
2. How does redshift differ by class? (histogram, bar chart of means)
3. How many records were observed per year, and has the class mix changed? (time-series line chart)
4. Where in the sky are the objects, and do classes cluster differently? (scatter of alpha vs delta)
5. Which class is brightest or faintest on average in the r band? (groupby)


## Dataset provenance 

The notebook loads a local file named `star_classification.csv` (100,000 rows
x 18 columns: `obj_ID, alpha, delta, u, g, r, i, z, run_ID, rerun_ID, cam_col,
field_ID, spec_obj_ID, class, redshift, plate, MJD, fiber_ID`).



obj_ID = Object Identifier, the unique value that identifies the object in the image catalog used by the CAS
alpha = Right Ascension angle (at J2000 epoch)
delta = Declination angle (at J2000 epoch)
u = Ultraviolet filter in the photometric system
g = Green filter in the photometric system
r = Red filter in the photometric system
i = Near Infrared filter in the photometric system
z = Infrared filter in the photometric system
run_ID = Run Number used to identify the specific scan
rereun_ID = Rerun Number to specify how the image was processed
cam_col = Camera column to identify the scanline within the run
field_ID = Field number to identify each field
spec_obj_ID = Unique ID used for optical spectroscopic objects (this means that 2 different observations with the same spec_obj_ID must share the output class)
class = object class (galaxy, star or quasar object)
redshift = redshift value based on the increase in wavelength
plate = plate ID, identifies each plate in SDSS
MJD = Modified Julian Date, used to indicate when a given piece of SDSS data was taken
fiber_ID = fiber ID that identifies the fiber that pointed the light at the focal plane in each observation



This is a well-known public dataset  **"Stellar Classification
Dataset - SDSS17"** on Kaggle (curated by fedesoriano, sourced from SDSS DR17).

Acknowledgements
The data released by the SDSS is under public domain. Its taken from the current data release RD17.


- Source URL: *https://www.kaggle.com/datasets/fedesoriano/stellar-classification-dataset-sdss17*
- Owner / creator: *fedesoriano *
  
- Download date: *Monday 2nd november 2026*




## Team

*(Add member names and assigned roles here.)*
