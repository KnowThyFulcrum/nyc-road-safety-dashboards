# NYC Road Safety Dashboards (Tableau)

Interactive Tableau dashboards analyzing NYC motor-vehicle collisions from 2020–2021: what causes collisions, where they happen, and how severe the high-risk intersections are.

**Course:** CNT 6152 – Advanced Data Visualization in ECE, Florida International University (Spring 2026) — team project

## Tools
Tableau · Python (pandas, NumPy) · Jupyter / Google Colab

## Methods
- **Data prep** (`notebooks/report_cleaning.ipynb`): filtered to 2020–2021; dropped rows missing borough/latitude/longitude (needed for the hotspot map); filled the single missing injured value with 0; kept the most useful columns; consolidated the five contributing-factor columns into one; removed records without proper intersection info.
- Starting from 223,000+ rows, the cleaned dataset had **141,727 records and 12 columns**.
- Built calculated fields in Tableau (e.g., collision category, intersection name) and dashboards answering:
  1. What causes collisions?
  2. Where do they happen?
  3. How bad are the high-risk spots?

## Key findings (from the project report)
- Human error is the biggest cause of collisions.
- Brooklyn and Queens had the most collisions (about 29K and 26K).
- The pandemic had a large temporary effect on collision counts, but the share of human-error crashes stayed consistently high.
- Some intersections, such as West Fordham Rd & Major Deegan Expwy and Rockaway Blvd & Brewer Blvd, had very high casualty counts. Complex junctions where 7 streets or ramps meet had significantly higher casualties.

## Repository structure
```
dashboards/final_project.twbx      Packaged Tableau workbook (includes its data extract) — open this one
dashboards/project_adv_viz.twb     Unpackaged workbook (expects the cleaned CSV in ./data)
notebooks/report_cleaning.ipynb    Data cleaning notebook
data/collisions_sample.csv         98-row sample of the raw data
docs/project_report.pdf            Project report
```

## Dataset
NYC Open Data — [Motor Vehicle Collisions – Crashes](https://data.cityofnewyork.us/Public-Safety/Motor-Vehicle-Collisions-Crashes/h9gi-nx95) (filter to 2020-01-01 – 2021-12-31). The full CSV is not committed separately; the packaged `.twbx` already contains the data it needs.

## How to run
- **Dashboards:** open `dashboards/final_project.twbx` in Tableau Desktop or the free Tableau Public app.
- **Cleaning:** `pip install -r requirements.txt`, download the dataset, then run the notebook. In Colab it uses `files.upload()`; locally, replace that cell with `pd.read_csv(...)`.

## Credits
Team project for CNT 6152. Contributor: Jay Cespedes.
