# Findings Summary — SDSS DR17 Stellar Classification
**DSA 1080A · Group 10 · Project 10: Space Observation and Satellite Data Trends**
Dataset: SDSS DR17 cleaned in Week 3, 99,999 records x 28 columns (100,000 x 18 raw). Figures are in `visuals/`; code is in `notebooks/04_visualization.ipynb`.

## Data-backed conclusions

1. **Redshift separates the three classes most clearly.** Mean redshift is 1.72 for quasars, 0.42 for galaxies and about 0 for stars (Figures 2 and 3). About 80% of quasars have z > 1 compared with 1.5% of galaxies, which fits stars being local and quasars being very distant.
2. **The sample is dominated by galaxies, and brightness follows distance.** Galaxies are 59.4% of records, stars 21.6% and quasars 19.0% (Figure 1). Median r magnitudes are 18.96 (stars), 20.10 (galaxies) and 20.77 (quasars), so the nearest class appears brightest and the most distant faintest (Figure 6).
3. **The observation mix and sky coverage are uneven.** Records peak at about 11,000 in 2011-2012, and the quasar share rises from about 16% (2010) to about 44% (2018) (Figure 4). Over half of objects lie between alpha = 120 and 240 degrees, 88% are in the northern sky, and large areas are empty (Figure 5).

## Practical recommendations

1. **Always report statistics per class, never only overall.** Because galaxies make up almost 60% of records, an overall average of redshift or brightness mostly describes galaxies. Automated sky-survey summaries should show a per-class table next to any total.
2. **Flag year and sky-region coverage in any automated summary.** Since the class mix changes by year and the footprint leaves large gaps, summaries should state the observation period and area covered, and survey planners can use the gaps in Figure 5 as candidates for future pointings.

## Limitations
The data are objects SDSS chose to observe, not a random sample of the sky, so shares and trends describe the survey and not the universe. Apparent brightness mixes distance with true luminosity.
