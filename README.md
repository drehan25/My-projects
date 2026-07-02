# Danish Rehan — Data Analytics Portfolio

Hi, I'm Danish Rehan, a junior at the University of Texas at Dallas 
studying Business Analytics and Artificial Intelligence. This repository 
contains the Python scripts and analysis code behind my data projects.

## Projects
# COVID-19 Global Analysis Dashboard

An interactive dashboard exploring global COVID-19 outcomes — cases,
deaths, vaccinations, and the country-level factors that shaped them.
Built in **Excel** and **Tableau**, with a **Python script** that
reproduces the analysis from the raw data.

## What this project answers

- How did cases and deaths differ across the six continents?
- Which countries were hit hardest (in raw numbers and per million people)?
- How far did vaccination rollouts get, and where were the gaps?
- Do a country's characteristics — wealth, age, hospital capacity —
  predict how badly COVID hit it?
- How did the pandemic rise and fall over time, month by month?

## Key findings

- **Europe and the Americas carried the heaviest toll.** Europe alone
  recorded over 1 million deaths, and South America had the highest
  average death rate (~2.7%).
- **Per-million numbers tell a fairer story.** Adjusting for population,
  Europe had by far the highest cases and deaths per million —
  population-adjusted metrics reveal impact that raw totals hide.
- **Older populations were the strongest risk signal.** A country's
  median age and share of people 65+ correlated most strongly with
  deaths per million — more than wealth or hospital capacity.
- **The "healthcare paradox":** countries with the *best* infrastructure
  often showed *higher* death rates, because they also have older
  populations — a reminder that no single factor explains outcomes.

## Data

- **Source:** [Our World in Data — COVID-19 dataset](https://ourworldindata.org/coronavirus)
- **Coverage:** ~210 countries, daily records, January 2020 – April 2021
- **Note:** Cumulative totals (cases, deaths, vaccinations) are reduced
  to one final value per country before aggregating.

## Files

| File | What it is |
|------|------------|
| `covid_analysis.py` | Python script that builds all the summary tables |
| `owid-covid-data.csv` | Raw source data (download from the link above) |
| `country_summary.csv` | Output: one row per country with key stats |
| `COVID-19 Dashboard.xlsx` | The Excel dashboard |
| Tableau workbook | The interactive Tableau version |

- **Tools:** Python, Pandas, Matplotlib
- **Full project:** danishrehan.com






### Bike Sales Analytics & Customer Segmentation
Analysis of 1,026 bike buyer records across 8 demographic and behavioral 
dimensions to identify the customer attributes that drive purchase 
conversion and define a target segment for the retailer.
- **Tools:** Python, Pandas, Excel, Tableau
- **Full project:** danishrehan.com

## Connect
- Portfolio: danishrehan.com
- LinkedIn: linkedin.com/in/danishrehan
- Email: dyr230001@utdallas.edu
