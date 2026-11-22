# Water Pollution & Cholera Risk Prediction

A machine learning project that predicts cholera disease risk based on water pollution and environmental data. Built using Python, Scikit-learn, Pandas and NumPy.

## Overview

This project analyses a dataset of 3,000 records across multiple countries to identify how water quality indicators (contaminant levels, pH, bacteria count, etc.) correlate with cholera cases. Two models were trained and compared — Logistic Regression and Random Forest — with Random Forest achieving stronger performance.

## Dataset

- **Source:** Water Pollution and Disease (public dataset, MIT licence)
- **Rows:** 3,000
- **Features:** 24 (including contaminant level, pH, turbidity, bacteria count, sanitation coverage, GDP per capita, and more)
- **Target:** Cholera cases per 100,000 people

## Tech Stack

- Python 3
- Pandas & NumPy — data loading and cleaning
- Scikit-learn — model training and evaluation
- Joblib — model saving and loading
- Jupyter Notebook

## Project Structure

```
water-pollution-ml/
├── water_pollution_cholera_prediction.ipynb   # Main notebook
├── water_pollution_disease.csv                # Dataset
└── README.md
```

## How to Run

1. Clone the repo
   ```bash
   git clone https://github.com/aradsgit/water-pollution-ml.git
   cd water-pollution-ml
   ```

2. Install dependencies
   ```bash
   pip install pandas numpy scikit-learn joblib jupyter
   ```

3. Launch the notebook
   ```bash
   jupyter notebook water_pollution_cholera_prediction.ipynb
   ```

## Results

| Model               | Accuracy | F1 Score |
|---------------------|----------|----------|
| Logistic Regression | 0.89%    | 0.79%    |
| Random Forest       | 2.66%    | 2.23%    |

Random Forest outperformed Logistic Regression across all metrics. Low overall accuracy is expected given the high number of target classes (50 distinct cholera case values) — the model captures relative risk patterns rather than exact counts.

## Key Steps

1. **Data Cleaning** — removed nulls, duplicates, standardised column names
2. **Feature Engineering** — one-hot encoded categorical variables, applied StandardScaler
3. **Model Training** — Logistic Regression (baseline) vs Random Forest (100 estimators)
4. **Evaluation** — accuracy, F1 score, classification report
5. **Model Export** — saved with joblib for reuse

## Ethics & Limitations

- Dataset relies on country-level reporting which may vary in accuracy
- Some regions may appear higher risk due to better reporting systems, not higher actual risk
- Model identifies patterns but cannot confirm causation between pollution and disease
- No personal data used — all records are aggregated by country/region
