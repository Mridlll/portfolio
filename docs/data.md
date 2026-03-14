# Data Engineering

Large-scale panel dataset construction, spatial harmonization, and survey microdata pipelines. All datasets are documented, reproducible, and published as open data.

---

## US Commuting Zone Panel (1980-2023)

**Demographics, Migration, Air Quality & Industry** | [GitHub](https://github.com/Mridlll/IUPMS-CZ-IRS-Dataset)

Comprehensive panel dataset covering 741 US Commuting Zones over 44 years with 72 variables. Built for research on environmental sorting, labor markets, and migration patterns.

**Data Sources Merged:**

| Source | Variables |
|--------|-----------|
| IPUMS USA | Demographics, education, income, housing |
| IRS SOI | County-to-county migration flows |
| EPA AQS | PM2.5, ozone concentrations |
| County Business Patterns | Industry composition, employment |
| QCEW | Quarterly wages, establishment counts |

??? info "Technical Details"

    - 1990 CZ definitions (Tolbert & Sizer) with David Dorn crosswalks
    - PM2.5 imputation via spatial (inverse distance weighting) and temporal (linear) interpolation
    - County-to-CZ aggregation using population weights
    - Skill group decomposition (high/low skill, young/old)

**Scale:** 6,422 CZ-year observations, 72 variables, 44-year span

Created as part of masters research at Heidelberg University on environmental sorting and spatial inequality.

**Stack:** Python (pandas, statsmodels), R (tidyverse)

---

## Indian District Banking Panel (2003-2022)

**Quarterly SCB Data from RBI DBIE** | [GitHub](https://github.com/Mridlll/-bsr-district-panel)

District-level quarterly panel of Scheduled Commercial Bank offices, deposits, and credit across India. Sourced from RBI DBIE Statement 4A, harmonized to Census 2001 (PC01) boundaries.

??? info "Harmonization Approach"

    - Two-pass district name matching (PC11 names first, then 2022-era names)
    - Telangana bifurcation handling (mapping back to pre-2014 AP boundaries)
    - Population group x bank group cross-tabulation panels
    - 13 districts dropped due to ambiguous boundary mapping

Co-authored with Vijayshree Jayaraman.

**Stack:** R (tidyverse, readxl, arrow/parquet)

---

## ASUSE Microdata (2021-2023)

**India's Unincorporated Sector Enterprise Survey** | [GitHub](https://github.com/Mridlll/ASUSE)

Cleaned microdata from India's Annual Survey of Unincorporated Sector Enterprises (NSS), covering 2021-22 and 2022-23. Analysis-ready outputs in Parquet, Stata (.dta), and CSV formats.

- Multi-level variable extraction from raw NSS text files using data dictionaries
- Variable labeling and preliminary cleaning
- Level-wise output for different survey modules

Co-maintained with Vijayshree Jayaraman and Advait Moharir.

**Stack:** Stata (cleaning do-files), R (format conversion)

---

## Crop Diversity Dataset

**725 Districts, 54 Crops, 24 Years** | [GitHub](https://github.com/Mridlll/crop-diversity)

District-level agricultural dataset with Shannon entropy, Simpson diversity, crop richness, and composite Agro-Biodiversity Index. Includes calorie-diversity overlays and irrigation regime stratification. Features interactive choropleth maps on GitHub Pages.

- District name harmonization across Census 2011 boundaries (96.6% coverage)
- IFCT 2017 energy conversion factors for calorie-weighted analysis
- Four-quadrant classification system for policy targeting

**Stack:** Python, pandas, geopandas, Folium

