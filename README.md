# Miami Housing Data Set Analysis

**What actually drives home prices in Miami?** An Excel analysis of **13,932 property sales** in Miami-Dade County, turned into a practical pricing framework for sellers, buyers and investors and presented as an 8-slide deck.

**Team:** Abidul Hasib · Ryan Farrar · James Lioy

---

## Key findings

| # | Finding | Evidence |
|---|---|---|
| 1 | **Living area is the strongest price driver.** Each extra square foot adds about **$260**. | r = 0.667, R² = 44.5% |
| 2 | **Special features and structure quality add clear premiums.** Quality 1 homes average $163K; Quality 5 homes average $743K. | Special features r = 0.497; quality r = 0.384 |
| 3 | **Ocean proximity is a major price layer.** Near-ocean homes (under 5,000 ft) average **$988K**, compared with $608K (medium) and $334K (far). | Ocean distance r = −0.275 |
| 4 | **Prices are right-skewed.** The median is **$310K** but the mean is **$400K**, pulled up by luxury sales up to $2.65M. | 736 sales at $1M+; IQR $235K–$428K |
| 5 | **Age matters only a little.** Older homes sell for slightly less, but age alone explains just 1.5% of price variation. | r = −0.123, R² = 1.5% |
| 6 | **High quality offsets age.** Quality 5 homes beat the market average in every age group. New Quality 5 homes average about $999K. | Age × quality summary |
| 7 | **Size bands show a 3× price gap:** large homes average $690K, medium $350K and small $232K. | Living-area groups |

### Main price drivers (correlation with sale price)

| Living area | Special features | Structure quality | Land size | Highway distance | Age | Centre distance | Ocean distance |
|---|---|---|---|---|---|---|---|
| **+0.667** | +0.497 | +0.384 | +0.363 | +0.232 | −0.123 | −0.271 | −0.275 |

---

## Pricing framework

The analysis turns into a five-step approach for pricing any Miami property:

1. **Baseline:** start from the median and the property's price band.
2. **Size:** adjust for living area, the strongest driver.
3. **Quality:** add premiums for structure quality and special features.
4. **Location:** apply the ocean-distance and city-centre-distance band.
5. **Validate:** check comparable sales in the same segment and set aside luxury outliers.

> These are correlations and segment patterns, so they support pricing decisions but don't prove that any one factor causes a price change.

---

## The dataset

`data/miami-housing.csv` has 13,932 rows and 17 columns, with no missing values.

| Column | Meaning |
|---|---|
| `SALE_PRC` | Sale price ($) |
| `TOT_LVG_AREA` | Living area (sq ft) |
| `LND_SQFOOT` | Land area (sq ft) |
| `SPEC_FEAT_VAL` | Value of special features, e.g. a pool ($) |
| `structure_quality` | Building quality, 1 (low) to 5 (high) |
| `age` | Age of the property (years) |
| `OCEAN_DIST`, `WATER_DIST`, `CNTR_DIST`, `SUBCNTR_DI`, `HWY_DIST`, `RAIL_DIST` | Distance (ft) to the ocean, nearest water, Miami city centre, nearest sub-centre, highway and rail line |
| `avno60plus` | 1 if the home is affected by airplane noise above 60 dB |
| `month_sold` | Month of sale (1–12) |
| `LATITUDE`, `LONGITUDE`, `PARCELNO` | Location and parcel ID |

---

## What's in the Excel workbook

`excel/miami_housing_analysis2Final.xlsx` has 8 sheets:

| Sheet | What it does |
|---|---|
| **HousingData** | The full dataset plus 4 helper columns built with formulas: Age Group, Living Area Group, Ocean Distance Band and Price Band |
| **Data Quality** | Checks for row and column counts, missing values, value ranges, formula errors and repeat parcel sales (152 parcels sold more than once) |
| **Univariate Analysis** | Descriptive statistics, histograms and box-plot summaries for 7 key variables (13 charts) |
| **Bivariate Analysis** | Scatter plots with trendlines, plus Pearson r, R², slope, intercept and p-value for each price driver (10 charts) |
| **Multivariate Analysis** | Age × quality, month × size and other cross-tabs, plus a correlation matrix (4 charts) |
| **BIV Pivot Tables** | Interactive PivotTables of average price by quality, month and other categories |
| **MULTI Pivot Tables** | Multi-dimensional PivotTables with slicers |
| **Executive Summary** | Objective, key findings, outliers, limitations and conclusion |

**Excel skills used:** descriptive statistics, nested `IF` banding, correlation and linear regression, histograms and box plots, scatter plots with trendlines, PivotTables, slicers and data-quality checks.

---

## The presentation

`presentation/miami_housing_findings_presentation.pptx` covers the findings in 8 slides:

1. Title and key question
2. Problem and approach
3. Market snapshot: price distribution
4. Main price drivers
5. Location premium: ocean proximity
6. Interactions: quality, age and size
7. A practical pricing framework
8. Recommended actions and conclusion

---

## Repository structure

```
Miami-Housing-Data-Set-Analysis/
├── data/           miami-housing.csv
├── excel/          miami_housing_analysis2Final.xlsx
├── presentation/   miami_housing_findings_presentation.pptx
└── README.md
```

## Limitations
- No neighbourhood, school-district or zoning data.
- Linear correlations can miss non-linear effects. That's why location is also analysed in distance bands.
- 16 homes rated Quality 3 have unusually high prices (average $1.85M), which distorts the Quality 3 average.
- 152 parcels appear more than once (repeat sales).
- The data covers a single period, so it shows no long-term market trends.

## Tools
Microsoft Excel (formulas, statistics, charts, PivotTables, slicers) · Microsoft PowerPoint
