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

`cars_6_to_10.loc[:, ['Model', 'mgp', 'cyl', 'hp', 'gear']]` / `df.loc[6:10, ['Model', 'mgp', 'cyl', 'hp', 'gear']]`: Selects specific columns using label-based indexing while keeping the subsetted rows intact. 

**Below is the complete Python code implementation for this problem:**
```

cars = pd.read_csv('cars.csv')
df = carsl

print(df.shape)
print(list(df.columns))

cars_6_to_10 = cars.iloc[6:11]
df.loc[6:10, ['Model', 'mgp', 'cyl', 'hp', 'gear']]
```
## B. Model Lookup
**Objective:** Use Boolean indexing on the `Model` column to locate specific vehicle models without hard-coding row number.

**Key functions and methods used in this problem:**
`df.['Model'] == 'Toyota Corolla'`: Generates a Boolean Series (mask) returning `True` for rows matching the specidied vehicle name.

`df.loc[condition]`: Filters the DataFrame based on the Boolean mask to extract matching rows.

`df.loc[condition, ['Model', 'mgp', 'hp', 'wt']]`: Combines Boolean indexing for row selection with explicit label selection for target columns. 

**Below is the complete Python code implementation for this problem:**
```
toyota = df.loc[df['Model']=='Toyota Corolla']
print(toyota)

Pontiac = df.loc[df['Model']=='Pontiac Firebird', ['Model', 'mpg','hp', 'wt']]
print(Pontiac)
```
## C. Multi-Model Subsetting
**Objective:** Create a subset named `selected_cars` containing records for three specific car models (`Datasum 710`, `Lotus Europa`, `Ferrari Dino`), showing only the `Model`,`mpg`, `cyl`, `hp`, and `gear` columns.

**Key functions and methods used in this problem:**
`.isin(['Datasum 710', 'Lotus Europa', 'Ferrari Dino'])`: Checks wheater elements in the `Model` column are contianed in the specidied target array/list.
`d.loc[mask, columns]`: Performs simultaneous row filtering via `.isin()` and column selection via exact column label lists. 

**Below is the complete Python code implementation for this problem:**
```
selected_cars = df.loc[df['Model'].isin(['Datsun 710', 'Lotus Europa', 'Ferrari Dino']), ['Model','mpg', 'cyl', 'hp', 'gear']]
print (selected_cars)
```

**Required Check (`selected_cars.shape`): ** `(3,5)` (3 rows, 5 columns)

--END--

To access the main Google Colab Notebook for Programming Assignment 3, click this link: https://colab.research.google.com/github/jasminemontillana/ECE2112_PA3/blob/main/Programming_Assignment_3.ipynb 

**README File Version History:**

September 8, 2026 Initial Commit

September 9, 2026 Update README 
