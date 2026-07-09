# Employee Data Cleaning Project

## Overview
A data cleaning project built with Python using pandas and NumPy. 
The goal was to take a raw, messy employee dataset and transform it 
into a clean, analysis-ready format by handling missing values, 
removing duplicates, fixing invalid data, and generating summary statistics.

## What This Project Does

### Problems Found in Raw Data
- Missing values across multiple columns (Name, Gender, Team, Salary, Bonus)
- Completely empty rows with no useful data
- Duplicate records
- Negative values in Salary and Bonus % columns (invalid business data)
- Missing salary values that needed intelligent replacement

### How Each Problem Was Fixed

**Missing Values:**
- Dropped rows where all values were empty
- Dropped rows missing critical fields: First Name, Gender, Team, Senior Management
- Replaced missing Salary values with the column mean rather than dropping records

**Invalid Data:**
- Converted negative Salary values to the column mean
- Converted negative Bonus % values to the column mean

**Duplicates:**
- Removed all duplicate rows

**Feature Engineering:**
- Calculated average salary per department team using groupby transform
- Generated full statistical summary (count, mean, std, min, max) exported to CSV

## Tools Used

| Tool | Purpose |
|---|---|
| Python | Core programming language |
| pandas | Data loading, cleaning, transformation |
| NumPy | Conditional value replacement using np.where |
| CSV | Input data source and output export |

## Key pandas and NumPy Functions Used
- `pd.read_csv()` — load raw data
- `df.isnull().sum()` — identify missing values
- `df.dropna()` — remove empty rows and rows missing critical fields
- `np.where()` — conditional replacement of nulls and negative values
- `df.drop_duplicates()` — remove duplicate records
- `df.groupby().transform()` — calculate department-level salary averages
- `df.describe()` — generate statistical summary
- `df.to_csv()` — export clean results

## Project Structure

```
employee-data-cleaning/
│
├── data_clean.ipynb     # Main Jupyter notebook with all cleaning steps
├── employees.csv        # Raw input dataset
├── description.csv      # Statistical summary output
└── README.md
```

## Skills Demonstrated
- Real-world data quality issues identification
- Missing value strategy — drop vs fill based on business logic
- Invalid data detection and correction
- Aggregation and feature engineering with groupby
- Clean, commented, step-by-step notebook structure
