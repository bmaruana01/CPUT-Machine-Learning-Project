# CPUT-Machine-Learning-Project
THis is where i created my third machine learning model 

# Data Cleaning: Registration Data 2025

This repository contains a Python script designed to clean and preprocess the `Registration_Data_2025` dataset. The script handles missing values, standardizes text formatting, corrects data types, and extracts useful features from date columns to prepare the data for analysis or machine learning models.

##  Dataset Overview

The dataset consists of student registration records containing demographic, academic, and institutional information. Key columns include:
- `Identifier` (Unique Student ID)
- `Matric Date` (Format: YYYYMM)
- `Age at Year_Beginning`
- `School Quintile`
- `Gender`, `Language Name`, `Qualification Type`, etc.

## Data Cleaning Steps

The Python script (`clean_data.py`) performs the following operations:

### 1. Initial Setup & Column Standardization
- Loads the raw dataset (`.csv`).
- Creates a copy of the dataframe to preserve the original raw data.
- Strips trailing and leading whitespaces from all column names.


### 3. Correcting Numeric Data Types
- **`School Quintile`**: Fills missing values with the median and converts the column from `float64` to `int64`.
- **`Age at Year_Beginning`**: Fills missing values with the median age and converts from `float64` to `int64`.
- **`Previous Activity Desc`**: Fills missing values with `0` and converts to `int64`.

### 4. Standardizing Categorical Text Data
- Identifies all text-based (`object`) columns.
- Strips whitespace, converts text to Title Case (e.g., "MALE" -> "M"), and fills missing values with "Unknown".
- Standardizes specific columns (e.g., converting "Male" and "Female" to "M" and "F" in the `Gender` column).
- Standardizes specific columns (converting Not Entering to Not Registered, and First time entering, Entering and Transfer to Registering).
- Standardizes `Post Graduate` values into consistent "Yes"/"No" formats.

### 5. Deduplication
- Removes duplicate rows based on the unique `Identifier` column, keeping only the first occurrence.

### 6. Export
- Saves the fully cleaned dataset as `Registration_Data_2025_Cleaned.csv` without the pandas index column.


