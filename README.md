# Analysing Data Strike Patterns ⚡

A data analysis and visualization project exploring lightning strike patterns across the United States in 2018, with an interactive Streamlit dashboard for exploring the dataset.

## Overview

This project analyzes over 3.4 million recorded lightning strikes from 2018, covering:

- Data cleaning (handling duplicates, irrelevant columns, datatype conversion)
- Outlier detection and removal using the IQR method
- Time-based aggregation (strikes per month)
- Visualization of strike frequency trends over the year

## Project Structure

```
.
├── Lightning_Strike_ipynb.ipynb   # Full analysis notebook (EDA, cleaning, visualization)
├── stream.py                       # Streamlit app for interactive dataset overview
├── Lightning Strike(2018).csv      # Raw dataset (not included in repo)
└── README.md
```

## Dataset

The dataset (`Lightning Strike(2018).csv`) contains the following columns:

| Column | Description |
|---|---|
| `date` | Date of the recorded strike(s) |
| `number_of_strikes` | Number of strikes recorded at that location/date |
| `x_coord` | Longitude coordinate |
| `y_coord` | Latitude coordinate |

> **Note:** The CSV file is not included in this repository due to its size (~3.4M rows). Place it in the project root before running the notebook or app.

## Notebook Walkthrough (`Lightning_Strike_ipynb.ipynb`)

1. **Importing Libraries and Dataset** – Loads the CSV using `pandas` and inspects shape/structure.
2. **Data Cleaning**
   - Converts `date` to a proper `datetime` object
   - Drops the unnecessary `Unnamed: 0` index column
   - Removes duplicate rows
   - Checks for null values
3. **Outlier Handling**
   - Visualizes `number_of_strikes` distribution with a boxplot
   - Computes Q1, Q3, and IQR
   - Filters out values beyond the upper bound
4. **Data Visualization**
   - Aggregates strikes by year-month
   - Plots a bar chart of strike counts per month

## Streamlit App (`stream.py`)

A lightweight dashboard that gives a quick overview of the dataset:

- Dataset sample preview
- Summary statistics (`describe()`)
- Column data types

### Running the app

```bash
pip install streamlit pandas plotly
streamlit run stream.py
```

Make sure `Lightning Strike(2018).csv` is in the same directory as `stream.py`.

## Requirements

- Python 3.10+
- pandas
- numpy
- matplotlib
- seaborn
- streamlit
- plotly

Install all dependencies:

```bash
pip install pandas numpy matplotlib seaborn streamlit plotly
```

## Key Insights

- Lightning strike frequency varies significantly by month, with peaks during warmer months.
- Raw strike counts contained outliers that skewed the distribution; the IQR method was used to produce a cleaner dataset for analysis.

## Author

Amanpreet Singh
