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


<br><br><br>
### Project 2
### Bike Sales Analytics & Customer Segmentation

Customer-profile analysis of **1,026 prospective bike buyers**, identifying which
demographic attributes best predict whether someone buys a bike — and defining the
single highest-converting target segment.

Built first in **Excel** (every figure is a live, auditable formula) and reproduced
in **Python/pandas** (`analysis.py`) so the core analysis is portable and verifiable
outside the workbook.

---

## TL;DR — Headline findings

| Metric | Value |
|---|---|
| Customers analyzed | 1,026 |
| Bikes purchased | 495 |
| **Baseline purchase rate** | **48.2%** |
| Avg. buyer income | $57,475 |
| Avg. buyer age | 42.8 |
| Avg. buyer # of cars | 1.21 |
| **Ideal-segment conversion** | **74.1%** (Pacific region + 0–1 mi commute) |

**Strongest predictor:** commute distance. Customers commuting **2–5 miles convert at
58.6%**, those commuting **10+ miles at just 29.2%** — a 29-point spread, the widest of
any attribute. Targeting the ideal profile lifts expected conversion from the 48%
baseline to **74%**.

> Surprising result: **income ranks only 6th**. Behavioral/lifestyle signals (commute,
> car ownership) separate buyers far better than raw earnings.

---

## Methodology

For each attribute we compute the **purchase rate** (buyers ÷ total) within every
segment, then rank attributes by the **spread** between their best- and worst-converting
segments. A wide spread means the attribute strongly separates buyers from non-buyers.

### Top predictors (ranked by max–min conversion spread)

| # | Predictor | Spread | Best-converting segment |
|---|---|---|---|
| 1 | Commute Distance | 29.4% | 2–5 Miles (58.6%) |
| 2 | Education | 26.1% | Bachelor's (54.3%) |
| 3 | # of Cars | 25.8% | 0 cars (60.2%) |
| 4 | Age Bracket | 23.4% | Middle Age 31–54 (54.7%) |
| 5 | Region | 15.6% | Pacific (58.9%) |
| 6 | Income Band | 12.7% | $40K–$80K (53.5%) |
| 7 | Marital Status | 11.3% | Single (54.3%) |
| 8 | # of Children | 9.5% | 1 child (57.0%) |

**A note on the Children predictor:** the spread is computed over **0–3 children only**.
Counts of 4 (n=126) and 5 (n=84) children are sparse and their purchase rates swing
widely (43% and 21%). Including them would vault Children to the *top* of the ranking
purely on the back of two small, noisy subgroups — a classic small-sample trap. Capping
at 0–3 keeps the ranking honest and matches the workbook.

---

## How the Excel dashboard works

The workbook is engineered for **full traceability** — no pasted numbers; every cell is a
formula tracing back to the raw table.

- **Raw data** lives in a table (`BikeBuyers`) with two derived helper columns:
  - `Age Bracket` = `IF(Age<31,"Adolescent (<31)",IF(Age<=54,"Middle Age (31-54)","Old (55+)"))`
  - `Income Band` = `IF(Income<40000,"<$40K",IF(Income<80000,"$40K-$80K",IF(Income<120000,"$80K-$120K","$120K+")))`
- **Filter engine:** a `Visible` column = `SUBTOTAL(103,[@ID])` returns 1 for rows passing
  the slicers and 0 otherwise. Every dashboard metric is a `SUMPRODUCT` weighted by
  `[Visible]`, so all KPIs and charts recalculate live as you slice.
- **KPIs** (examples):
  - Purchase rate = `SUMPRODUCT([Visible]*([Purchased Bike]="Yes")) / SUM([Visible])`
  - Avg buyer income = `SUMPRODUCT([Visible]*([Purchased Bike]="Yes")*[Income]) / SUMPRODUCT([Visible]*([Purchased Bike]="Yes"))`
- **Predictor spread** (per attribute) = `MAX(segment rates) − MIN(segment rates)`.
- **Ideal-profile conversion** = purchase rate within `Region="Pacific"` AND
  `Commute Distance="0-1 Miles"`.

---
## Connect
- Portfolio: danishrehan.com
- LinkedIn: linkedin.com/in/danishrehan
- Email: dyr230001@utdallas.edu

<br><br><br>
## AI-Powered Search Engine with Exa API

A Python-based search engine that uses the Exa API to retrieve 
real-time, relevant web results based on a user's query. Unlike 
traditional keyword-based search, Exa uses neural/semantic search 
to surface more contextually relevant results based on meaning 
rather than exact keyword matching.

## What It Does

- Accepts a user search query via the command line
- Lets the user choose how many results to return
- Searches the full web using neural/semantic search
- Returns results including title, URL, and a short summary
- Displays results in a clean, numbered format

## Demo
Search here: machine learning in healthcare

How many results would you like? 3
Top 3 results for: "machine learning in healthcare"
==================================================

Result 1:

Title:   How AI is Transforming Healthcare Diagnostics

URL:     https://example.com/ai-healthcare

Summary: Machine learning models are being used to detect

diseases earlier and more accurately than traditional

methods...
Result 2:

...

## Tech Stack

- Python 3
- Exa API (exa-py)

## Setup

1. Clone this repository
2. Install the required library:
pip install exa-py
3. Get a free API key at exa.ai
4. Replace YOUR_API_KEY_HERE in the script with your actual key
5. Run the script:
python exa_search.py

## Features

- **Neural Search** — Uses meaning-based retrieval instead of 
  exact keyword matching for more relevant results
- **Dynamic Result Count** — User chooses how many results 
  to return at runtime instead of a hardcoded number
- **Result Summaries** — Displays a short AI-generated summary 
  for each result alongside the title and URL
- **Full Web Search** — Searches across the entire web rather 
  than being restricted to specific domains
- **Clean Output Formatting** — Results are numbered and 
  separated for easy readability

## Key Concepts

- **API Integration** — Connects to an external API to fetch 
  live, real-time search results
- **Semantic/Neural Search** — Retrieves results based on 
  meaning and context rather than exact keyword matching
- **User Input Handling** — Accepts and validates runtime 
  input from the user for both query and result count

## Notes

This project was built as part of my data analytics portfolio 
to explore AI-driven information retrieval and external API 
integration. The API key in this script is a placeholder — 
get your own free key at exa.ai to run it locally.


## Connect
Portfolio: danishrehan.com
LinkedIn: linkedin.com/in/danishrehan
