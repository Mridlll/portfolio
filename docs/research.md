# Economics Research

Causal inference, spatial econometrics, and policy evaluation across development, environmental, and urban economics.

---

## Sorting Into Pollution

**Labor Market Access, Information, and the Location Decisions of Young Workers** | MSc Thesis, Heidelberg University

[:material-web: Interactive Showcase](https://mridlll.github.io/Sorting-Into-Pollution/){ .md-button } [:material-file-pdf-box: Full PDF](https://mridlll.github.io/Sorting-Into-Pollution/thesis.pdf){ .md-button .md-button--primary } [:material-github: Repository](https://github.com/Mridlll/Sorting-Into-Pollution){ .md-button }

Young low-skill workers systematically sort into polluted commuting zones without receiving compensating wage differentials. Using NOAA's HYSPLIT atmospheric trajectory model as an instrumental variable, this paper documents a market failure that costs $4.66 billion annually and falls disproportionately on Black workers.

??? info "Identification & Methodology"

    - Instrumental variable: upwind PM2.5 from HYSPLIT 72-hour backward trajectories (F = 184.7)
    - Panel data: 247 commuting zones, 13,569 CZ-year observations (2000-2019)
    - Demographic data: IPUMS ACS 1-year samples, 239M individual records
    - Pollution data: ACAG satellite-derived PM2.5 (Washington University)
    - Robustness: Conley spatial SEs, permutation inference, Oster bounds, placebo tests

**Key Findings:**

| Result | Estimate |
|--------|----------|
| IV coefficient (10% PM2.5 increase) | +1.37 pp young worker share |
| Compensating wage differential | None (n.s.) |
| Manufacturing mechanism | ~30% of sorting explained |
| Temporal decline (2000-2019) | ~80% reduction |
| Racial disparity (Black vs. White) | +22% stronger sorting |
| Annual welfare cost (national) | $4.66 billion |

**Stack:** Python, statsmodels, linearmodels, D3.js, LaTeX/MiKTeX

---

## Agricultural Intervention Impact Evaluation

**Sustainable Farming Practice Adoption in South India** | [GitHub](https://github.com/Mridlll/APCNF-demo)

Full econometric pipeline assessing the impact of a sustainable agricultural intervention on ~900 smallholder farmers in southern India. Conducted for a leading energy and environment think tank.

??? info "Methodology"

    - ANCOVA with district fixed effects, clustered standard errors (~75 clusters)
    - Inverse Hyperbolic Sine (IHS) transformation for cost variables with zeros
    - Propensity Score Matching & Inverse Probability Weighting
    - Oster bounds for selection on unobservables
    - Benjamini-Hochberg FDR correction for multiple hypothesis testing
    - Heterogeneity analysis by caste, education, farm size
    - Agro-climatic zone stratification

**Key Findings:**

| Outcome | Direction |
|---------|-----------|
| Women's empowerment | Significant positive effect |
| Home garden adoption | ~20 pp increase |
| Chemical input costs | Dropped by 85-95% |
| Diet diversity (adopters) | Significant improvement |

**Stack:** Python, statsmodels, linearmodels, matplotlib, Plotly, LaTeX/Beamer

---

## Crop Diversification in India (1997-2021)

**District-Level Agricultural Biodiversity Analysis** | [GitHub](https://github.com/Mridlll/crop-diversity)

Comprehensive analysis of crop diversification across 725 Indian districts, 54 crops, and 24 agricultural years. Features interactive choropleth maps hosted on GitHub Pages.

??? info "Methodology"

    - Shannon entropy, Simpson diversity, Crop Richness, composite Agro-Biodiversity Index (ABI)
    - Calorie-diversity overlay using IFCT 2017 energy conversion factors (kcal/ha)
    - Four-quadrant classification: Diverse & Calorie-Rich, Monoculture Breadbasket, Diverse & Calorie-Poor, Vulnerable
    - Irrigation regime stratification (Rainfed / Semi-Irrigated / Irrigated)
    - District name harmonization across Census 2011 boundaries (96.6% coverage, 710/735 districts)

**Key Findings:**

- Semi-irrigated districts are the most diverse (ABI 0.69), outperforming both rainfed (0.62) and fully irrigated (0.67)
- 357 districts losing diversity vs. 233 gaining nationally
- Irrigated districts allocate 67% of area to cereals, crowding out pulses and oilseeds
- The assumed diversity-productivity tradeoff is overstated: correlation shifts from -0.18 to +0.02 when coconut-dominant districts are excluded
- Karnataka is the most diverse state (ABI 0.85), Punjab the least (0.44)

**Stack:** Python, pandas, geopandas, Plotly, Folium, interactive maps

---

## Bilal & Kanzig (2024) Replication

**The Macroeconomic Impact of Climate Change** | [GitHub](https://github.com/Mridlll/micc_replication)

Full replication of Bilal & Kanzig's "The Macroeconomic Impact of Climate Change: Global vs. Local Temperature" — forthcoming in the *Quarterly Journal of Economics*.

??? info "Methodology"

    - Time-series and panel local projections
    - Bootstrap inference and VAR analysis
    - Quantitative climate-economy model with damage process estimation
    - Transition path computation
    - Welfare and Social Cost of Carbon (SCC) calculation

Covers both the empirical analysis (Stata 16.1) and the full structural model (MATLAB 2024b). All figures, tables, and quantitative results are reproducible in approximately 20 minutes.

**Stack:** Stata, MATLAB

---

## Prime Locations & Environmental Justice

**Intra-Urban Pollution Gradients** | Private repository

Extending Ahfeldt's "prime locations" framework to study how air pollution (PM2.5) creates environmental sorting within US Metropolitan Statistical Areas. Panel analysis across 741 commuting zones with IV identification strategy.

??? info "Methodology"

    - PanelOLS with MSA fixed effects and clustered standard errors
    - PM2.5 zonal statistics extraction from EPA monitors
    - Historical instrument approach for IV analysis
    - Distance gradient estimation (binscatters)

**Stack:** Python, linearmodels, geopandas, Census API, EPA AQS

---

## Medicaid CDPAP Investigation

**New York's $69B Personal Care Story** | Current work

Data journalism-style analysis of Consumer Directed Personal Assistance Program (CDPAP) spending patterns. Investigative figures combining FT/NYT editorial style with choropleth mapping and NPI-level provider analysis.

**Stack:** Python, matplotlib, geopandas

