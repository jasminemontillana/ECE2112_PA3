# ECE2112_PA3
Created by: Montillana, Jasmine Marie P. | 2ECE-B

This repository contains the completed Programming Assignment 3 for ECE2112: Advance Computer Programming and Algorithms. The project covers Pandas DataFrames, indexing, positional (`iloc`) and label-based (`loc`) slicing, Boolean conditions, subsetting, and multi-model data extraction using the `cars.csv` dataset without modify the source data.

## A. Positional and Label-Based Slicing
**Objective:** Load the `cars.csv` dataset into a DataFrame named `cars`, inspect its dimensions and column names, and create a subset containing rows 6 through 10 with specified columns (`Model`, `cyl`, `hp`, and `gear`).

**Key functions and methods used in this problem:**
`pd.read_csv('cars.csv')`: Reads a comma-separated values (CSV) file into a Pandas DataFrame.
`.shape`: A DataFrame attribute that returns a tuple representing its dimensionality `(rows,cloumns)`.
`list(df.columns)`: Extracts the full list of column headers from the DataFrame as a Python list. 
`cars.iloc[6:11]`: Selects rows by zero-based positional indexing (rows 6 through 10, inclusive, corresponding to index range `6:11`).
`cars_6_to_10.loc[:, ['Model', 'mgp', 'cyl', 'hp', 'gear']]`
