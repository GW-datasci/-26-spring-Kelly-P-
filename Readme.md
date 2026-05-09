# Modeling Global Climate Change News: A Computational Analysis of Media Tone Across Countries

**Author:** Priya G. Kelly  
**Course:** DATS 4001 — Data Science Capstone, Spring 2026  
**Supervisor:** Prof. Sushovan Majhi  
**University:** The George Washington University, Data Science Program

---

## Project Overview

This project analyzes how the tone of climate change news coverage varies across countries using data from the Global Database of Events, Language, and Tone (GDELT) for the year 2024. Climate-related articles were pulled from GDELT via Google BigQuery, thematic features were extracted and reduced from ~4,000 to 98 variables, and a multiple linear regression model was trained to predict country-level average tone. The model achieved R² = 0.365 across 118 countries.

---

## Repository Structure

```
-26-spring-Kelly-P-/
├── data/                   # Data files used in the analysis
├── demo/
│   └── CleanedandFeatureEngineering__4_.ipynb   # Main Jupyter notebook
├── poster/                 # Capstone poster
├── presentation/           # Presentation slides
├── proposal/               # Project proposal
├── report/                 # Final LaTeX report
├── requirements.txt        # Python dependencies
└── Readme.md               # This file
```

---

## How to Reproduce the Results

### Step 1 — Clone the repository

```bash
git clone https://github.com/GW-datasci/-26-spring-Kelly-P-.git
cd -26-spring-Kelly-P-
```

### Step 2 — Install dependencies

Make sure you have Python 3.x installed, then run:

```bash
pip install -r requirements.txt
```

### Step 3 — Set up Google BigQuery access

The data is pulled from GDELT via Google BigQuery. You will need:
- A Google account with BigQuery access
- The `google-cloud-bigquery` Python library (included in requirements.txt)
- Authentication via `gcloud` or a service account credentials file

To authenticate, run:

```bash
gcloud auth application-default login
```

### Step 4 — Run the notebook

Open the notebook in Jupyter:

```bash
jupyter notebook demo/CleanedandFeatureEngineering__4_.ipynb
```

Run all cells from top to bottom (**Kernel → Restart & Run All**) to reproduce the full pipeline including data processing, feature engineering, model training, and visualizations.

---

## Reproducibility Settings

| Setting | Value |
|---|---|
| Random seed (`random_state`) | 42 |
| Train/test split | 80% train, 20% test |
| Number of countries | 118 |
| Final number of features | 98 |
| Model | Multiple Linear Regression (OLS) |
| Key library | scikit-learn |

---

## Main Result

The multiple linear regression model achieved **R² = 0.365** on the held-out test set, meaning thematic features derived from GDELT explain approximately 36.5% of the variance in country-level average climate news tone across 118 countries in 2024.

---

## Dependencies

All dependencies are listed in `requirements.txt`. Key libraries:

- `pandas` — data manipulation
- `scikit-learn` — preprocessing, modeling, evaluation
- `matplotlib` — visualization
- `geopandas` — geospatial mapping
- `google-cloud-bigquery` — GDELT data access

---

## AI/GAI Disclosure

Claude (Anthropic) and ChatGPT (OpenAI, GPT-4) were used during the modeling phase to help diagnose and resolve a negative R² caused by overfitting. All suggestions were independently verified and implemented by the author.
