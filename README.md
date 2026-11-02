# DSA 1080A — Group 10: Space Observation and Satellite Data Trends

**Course:** DSA 1080A, Programming for Data Science — Future Data Lab (Five-week group project)
**Group:** 10
**Project option:** 10 — Space Observation and Satellite Data Trends
**Dataset:** SDSS DR17 stellar classification data (stars / galaxies / quasars)

> Status: Week 1 scaffolding. Sections below are marked **(TBD)** where the work
> is genuinely not done yet — this repo is being built incrementally over the
> five weeks of the project, and nothing below claims future-week work is complete.

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
6. Bonus: when the same `obj_ID` was observed repeatedly, did the class label always agree?

## Dataset provenance — needs confirmation

The notebook loads a local file named `star_classification.csv` (100,000 rows
x 18 columns: `obj_ID, alpha, delta, u, g, r, i, z, run_ID, rerun_ID, cam_col,
field_ID, spec_obj_ID, class, redshift, plate, MJD, fiber_ID`).

This matches a well-known public dataset, likely **"Stellar Classification
Dataset - SDSS17"** on Kaggle (curated by fedesoriano, sourced from SDSS DR17).
**This is an inference and is not yet confirmed** — the assignment brief
requires the exact source URL, owner, license and download date to be recorded
and defended, so **Kael/the group needs to verify and fill in the details below**
before Week 1 submission:

- Source URL: *(TBD — confirm exact Kaggle link)*
- Owner / creator: *(TBD — believed to be "fedesoriano" on Kaggle)*
- License: *(TBD — confirm license terms on the Kaggle dataset page)*
- Download date: *(TBD)*
- Collection period / limitations: *(TBD)*

## Repository structure

```
.
├── README.md
├── requirements.txt
├── .gitignore
├── data/
│   ├── raw/            # Original CSV (or source link + download instructions) — see data/raw/README.md
│   └── processed/      # Cleaned data / reproducible cleaning script (Week 3)
├── notebooks/
│   ├── 01_foundations.ipynb       # Week 1 — done (this is Kael's transferred work)
│   ├── 02_exploration.ipynb       # Week 2 — stub, TODO
│   ├── 03_cleaning_analysis.ipynb # Week 3 — stub, TODO
│   └── 04_visualization.ipynb     # Week 4 — stub, TODO
├── visuals/             # Exported chart PNGs (Week 4) — TODO
├── report/
│   └── final_report.pdf           # Week 5 — TODO
├── presentation/
│   └── final_slides.pdf/.pptx     # Week 5 — TODO
└── docs/
    ├── data_dictionary.md         # Week 2 — stub, TODO
    └── cleaning_log.md            # Week 3 — stub, TODO
```

## How to run

1. Clone this repository.
2. Create a virtual environment and install dependencies:
   ```
   pip install -r requirements.txt
   ```
3. Add the dataset to `data/raw/` — see `data/raw/README.md` for details
   (the CSV is not committed to this repo yet; it needs to be added by a
   team member, either directly, via Git LFS, or linked to its source).
4. Open `notebooks/01_foundations.ipynb` in Jupyter and run the cells in order.

## What's done vs. what's left (as of Week 1 setup)

**Done:**
- Repository structure created per the assignment brief (section 3).
- `notebooks/01_foundations.ipynb` populated with Kael's actual Week 1 work:
  imports, loading the CSV, `df.shape` / `df.info()`, null check, `df.describe()`,
  and an initial class-distribution count/plot.
- Objectives and draft research questions documented (above), from Kael's own notebook.

**Still TBD / left as stubs for the team to fill in:**
- Confirming and documenting the exact dataset source URL, license and download date.
- Adding the actual CSV to `data/raw/` (or Git LFS / source link).
- `notebooks/02_exploration.ipynb`, `03_cleaning_analysis.ipynb`, `04_visualization.ipynb` — all future-week work, currently empty stubs.
- `docs/data_dictionary.md` and `docs/cleaning_log.md` — stubs, to be filled in Weeks 2–3.
- `visuals/` — empty, charts land here in Week 4.
- `report/final_report.pdf` and `presentation/final_slides.pdf`/`.pptx` — Week 5 deliverables, not started.
- Team/member names and assigned roles section (add here once agreed).

## Team

*(Add member names and assigned roles here.)*
