# DIGITZ Real Estate Data Intelligence

Independent research combining property data, market evidence and reproducible analysis to examine Accra’s residential ecosystems.

# Project overview

DIGITZ Real Estate Data Intelligence is an independent property intelligence and research organisation founded by Emmanuel Peprah. It examines how Accra’s residential property ecosystems differ in their housing composition, pricing architecture, tenure structure and wider market behaviour.

DIGITZ’s early exploratory work used manually collected property advertisements organised in Excel, with selected samples subsequently analysed in Python. The research programme has since expanded to include a purpose-built collection pipeline and a staged framework for dataset authentication and analysis. Authentication of the broader dataset remains in progress.

The guiding principle is:

> Evidence leads. Structure follows. Conclusions are earned.

## Research problem

Accra’s residential property market contains abundant listings but limited independent intelligence explaining how locations are structured, why they behave differently and how they function within the wider residential market. Listings indicate what is advertised and at what asking price, but do not on their own provide those explanations.

DIGITZ was established to investigate this gap by authenticating and comparing property data, then testing emerging explanations against wider market evidence.

## Founder’s analytical journey

My analytical foundation developed through financial operations analysis, where Excel became my first practical tool for examining performance and risk. This experience encouraged me to develop a background in data science, data analytics and Python.

Alongside this development, an interest in evidence-based investment led me to examine Accra’s residential property sector from the perspective of a prospective investor. Through this investigation, I encountered the research gap described above.

To deepen my understanding of the sector, I gained two years of direct industry experience in property operations, connecting patterns observed through data with operational realities. Building on these experiences, I established DIGITZ.

## Research purpose

DIGITZ studies residential locations as distinct but connected ecosystems within Accra. Its inaugural research programme covers ten locations:

- Airport Residential
- Cantonments
- East Legon
- Tse Addo
- Spintex
- Adenta
- Tema
- Osu
- Dzorwulu
- Dansoman

## Available analysis

### East Legon exploratory analysis

The East Legon notebook presents a reproducible Python analysis of an early, purposively selected sample of 222 property advertisements: 99 sale listings and 123 rental listings. The sample was drawn from DIGITZ’s earlier exploratory work across multiple ecosystems and organised in Excel. East Legon is presented as a reproducible Python example of that early analytical stage.

The notebook examines:

- dataset structure and record-level quality checks;
- property-type composition;
- bedroom composition;
- asking-price distributions and descriptive statistics;
- median asking prices by bedroom category;
- property type × bedroom × tenure relationships; and
- rental-to-sale listing ratios subject to a minimum reporting threshold.

| File | Purpose |
|---|---|
| [DIGITZ_East_Legon_Exploratory_Analysis.ipynb](exploratory-analysis/east-legon/DIGITZ_East_Legon_Exploratory_Analysis.ipynb) | Executed Python notebook containing the analysis, tables and charts |
| [DIGITZ_East_Legon_Exploratory_Data.xlsx](exploratory-analysis/east-legon/DIGITZ_East_Legon_Exploratory_Data.xlsx) | Supporting Excel workbook containing the sales and rental samples |

## Results from the exploratory sample

- Houses form the largest property-type share of the sales sample at 46.5%.
- Apartments form the largest property-type share of the rental sample at 52.8%.
- Three-bedroom listings are the modal bedroom category in both tenure samples.
- The median normalised sale asking price is approximately USD 281,715.
- The median normalised monthly asking rent is approximately USD 2,100.
- Sale and rental asking-price distributions are positively skewed, with skewness values of 2.17 and 1.19 respectively.
- Median asking prices increase with bedroom count in both tenure samples.

These results describe the selected advertisement dataset. They do not establish completed transaction prices, occupancy, demand or patterns representative of the entire East Legon residential market.

## Analytical approach used in the notebook

The notebook:

1. imports the separate sales and rental worksheets;
2. inspects columns, sample sizes and representative records;
3. checks missing values, categorical consistency and record-level duplicates;
4. calculates property-type and bedroom counts and percentages;
5. expresses asking prices in USD by applying a fixed analytical rate of GH₵11.43 per USD 1 to the workbook’s cedi price field;
6. calculates means, medians, quartiles, interquartile ranges, ranges and skewness;
7. examines median asking prices by bedroom category;
8. cross-tabulates property type, bedroom count and tenure; and
9. reports rental-to-sale listing ratios only where both tenure samples satisfy the minimum threshold.

The notebook keeps sale asking prices separate from monthly rental asking prices and retains townhouses as a distinct property category. All reported bedroom categories contain at least eight listings, satisfying the minimum reporting threshold for median and quartile statistics. Rental-to-sale ratios are interpreted only where both tenure groups contain at least eight listings.

The sample was manually reviewed before analysis, including individual listing checks and duplicate review. The notebook independently re-verifies record-level uniqueness across listing IDs, source URLs and complete rows. Counts and percentages are reconciled against sample totals at the end of the notebook.

These automated checks establish internal consistency within the supplied sample. They do not repeat the full manual listing verification or establish complete market coverage. Asking prices are not completed transaction prices.

## Repository structure

```text
digitz-real-estate-data-intelligence/
├── exploratory-analysis/
│   └── east-legon/
│       ├── DIGITZ_East_Legon_Exploratory_Analysis.ipynb
│       └── DIGITZ_East_Legon_Exploratory_Data.xlsx
├── README.md
└── .gitignore
```

East Legon is the first published exploratory analysis. Later work will be added alongside it as the relevant review is completed.

## Tools and methods

The published exploratory analysis uses:

- **Excel** for organising the manually collected listing sample.
- **Python and pandas** for data-quality checks, descriptive statistics and cross-tabulation.
- **Matplotlib** for charts of housing composition and asking-price patterns.
- **openpyxl** for reading the Excel workbook through pandas.
- **Jupyter Notebook or Google Colab** for running and viewing the analysis.

The methods are described in the Analytical approach section; calculations and saved outputs are available in the notebook.

## Reproducibility

The notebook is stored with its outputs, so the full analysis, tables and charts can be read directly on GitHub without installing anything. The saved run completed sequentially without errors, and its final reconciliation checks confirm the sample totals, category counts, percentages and currency calculations. The software versions used for the saved run are printed in the notebook’s environment cell.

### Requirements

- Python 3
- pandas
- Matplotlib
- openpyxl

### Run in Google Colab

1. Open `DIGITZ_East_Legon_Exploratory_Analysis.ipynb` from `exploratory-analysis/east-legon/` in Google Colab.
2. Upload `DIGITZ_East_Legon_Exploratory_Data.xlsx` to the Colab session.
3. Select **Runtime → Restart session and run all**.

### Run locally

1. Open a terminal in `exploratory-analysis/east-legon/`, where the notebook and workbook are stored together.
2. Install the requirements: `python -m pip install pandas matplotlib openpyxl notebook`
3. Start Jupyter with `jupyter notebook`, open `DIGITZ_East_Legon_Exploratory_Analysis.ipynb` and run all cells.

The workbook must retain the filename `DIGITZ_East_Legon_Exploratory_Data.xlsx` and the worksheet names `🏡 Sales Hub` and `🔑 Rentals Lounge`, because the notebook references them directly. It must be in the notebook’s working directory when the code runs.

## Data note

The East Legon listings were manually collected from Meqasa over a one-week period in early April 2026 and individually verified. Selection was purposive, with published ecosystem price benchmarks guiding the price range covered. Repeat advertisements identified as referring to the same property were excluded. Consequently, the price distribution and summary statistics describe the selected sample and should not be interpreted as estimates for the entire East Legon residential market.

The public workbook contains the sales and rental samples used in the notebook, with the agent and developer name column removed. Source URLs preserve listing provenance; linked pages may change, redirect or become unavailable after collection.

## Author

**Emmanuel Peprah**  
Founder and Lead Analyst, DIGITZ Real Estate Data Intelligence  
Accra, Ghana  
Website: [digitzgh.com](https://digitzgh.com/)  
Contact: [info@digitzgh.com](mailto:info@digitzgh.com)
