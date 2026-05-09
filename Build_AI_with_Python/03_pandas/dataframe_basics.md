# DataFrame Basics using Pandas

# Overview

DataFrames are the core data structure in Pandas.

They are widely used in:

* Artificial Intelligence
* Machine Learning
* Data Science
* Data Engineering
* Automation
* Analytics
* Scientific Computing
* VLSI Report Processing
* Hardware Simulation Analysis

A DataFrame stores data in:

* rows
* columns
* labeled structure

It is similar to:

* Excel spreadsheets
* SQL tables
* CSV files
* database tables

DataFrames make data:

* easier to organize
* easier to analyze
* easier to filter
* easier to process

---

# Why DataFrames are Important

Modern AI and analytics systems work with:

* structured datasets
* CSV files
* logs
* sensor data
* numerical tables

DataFrames provide:

* high-level data manipulation
* fast filtering
* statistical operations
* preprocessing pipelines
* scalable analysis systems

Without DataFrames:

* data handling becomes difficult
* preprocessing becomes slower
* analytics workflows become inefficient

---

# Learning Goals

By the end of this notebook, you will understand:

* What a DataFrame is
* How to create DataFrames
* Rows and columns
* Selecting data
* Adding columns
* Updating values
* Filtering data
* Sorting data
* Basic statistics
* Data inspection
* Real-world AI workflows
* Common beginner mistakes
* Best practices

---

# Import Pandas

```python id="p8w4xk"
import pandas as pd
```

`pd` is the standard alias for Pandas.

---

# 1. What is a DataFrame?

A DataFrame is a 2-dimensional tabular data structure.

It contains:

* rows
* columns
* labels

Think of it like:

| Name  | Age | Score |
| ----- | --- | ----- |
| Alice | 21  | 88    |
| Bob   | 25  | 92    |

This table is a DataFrame.

---

# Structure of a DataFrame

A DataFrame contains:

* index
* columns
* values

Visual Structure:

```text id="4wrjlwm"
        Name   Age   Score
0       Alice   21     88
1         Bob   25     92
2     Charlie   22     95
```

Where:

* left side numbers → index
* top labels → column names
* middle values → actual data

---

# 2. Creating a DataFrame

---

## Creating from Dictionary

```python id="g8jlwm"
import pandas as pd

data = {
    "Name": ["Alice", "Bob", "Charlie"],
    "Age": [21, 25, 22],
    "Score": [88, 92, 95]
}

df = pd.DataFrame(data)

print(df)
```

Output:

```text id="7jlwm"
      Name  Age  Score
0    Alice   21     88
1      Bob   25     92
2  Charlie   22     95
```

---

# Understanding the Output

Columns:

* Name
* Age
* Score

Rows:

* each row represents one record

Index:

* 0, 1, 2

---

# 3. Checking DataFrame Information

---

## Shape

```python id="9jlwm"
print(df.shape)
```

Output:

```text id="6jlwm"
(3, 3)
```

Meaning:

* 3 rows
* 3 columns

---

## Column Names

```python id="5jlwm"
print(df.columns)
```

---

## Data Types

```python id="3jlwm"
print(df.dtypes)
```

---

## General Information

```python id="2jlwm"
print(df.info())
```

Shows:

* total rows
* columns
* memory usage
* datatype information

---

# 4. Viewing Data

---

## First 5 Rows

```python id="1jlwm"
print(df.head())
```

---

## Last 5 Rows

```python id="0jlwm"
print(df.tail())
```

---

## Specific Number of Rows

```python id="11jlwm"
print(df.head(2))
```

---

# Why Data Inspection is Important

Used for:

* dataset understanding
* debugging
* AI preprocessing
* analytics validation

---

# 5. Selecting Columns

---

## Single Column

```python id="12jlwm"
print(df["Name"])
```

Output:

```text id="13jlwm"
0      Alice
1        Bob
2    Charlie
Name: Name, dtype: object
```

---

## Multiple Columns

```python id="14jlwm"
print(df[["Name", "Score"]])
```

---

# 6. Selecting Rows

---

## Using loc

`loc` uses labels.

```python id="15jlwm"
print(df.loc[0])
```

---

## Using iloc

`iloc` uses integer positions.

```python id="16jlwm"
print(df.iloc[0])
```

---

# Difference Between loc and iloc

| loc         | iloc          |
| ----------- | ------------- |
| label-based | integer-based |

---

# 7. Filtering Data

---

## Basic Filtering

```python id="17jlwm"
filtered = df[df["Score"] > 90]

print(filtered)
```

Output:

```text id="18jlwm"
      Name  Age  Score
1      Bob   25     92
2  Charlie   22     95
```

---

# Multiple Conditions

```python id="19jlwm"
filtered = df[
    (df["Age"] > 21) &
    (df["Score"] > 90)
]

print(filtered)
```

---

# Why Filtering Matters

Filtering is heavily used in:

* AI preprocessing
* analytics systems
* automation pipelines
* report analysis

---

# 8. Adding Columns

---

## Example

```python id="20jlwm"
df["Passed"] = df["Score"] > 50

print(df)
```

Output:

```text id="21jlwm"
      Name  Age  Score  Passed
0    Alice   21     88    True
1      Bob   25     92    True
2  Charlie   22     95    True
```

---

# 9. Updating Values

---

## Updating Entire Column

```python id="22jlwm"
df["Score"] = df["Score"] + 5

print(df)
```

---

## Updating Specific Cell

```python id="23jlwm"
df.loc[0, "Score"] = 100

print(df)
```

---

# 10. Deleting Columns

---

## Drop Column

```python id="24jlwm"
df.drop("Passed", axis=1, inplace=True)
```

---

# Why axis=1?

| axis | Meaning |
| ---- | ------- |
| 0    | rows    |
| 1    | columns |

---

# 11. Sorting Data

---

## Sort by Single Column

```python id="25jlwm"
sorted_df = df.sort_values(by="Score")

print(sorted_df)
```

---

## Descending Order

```python id="26jlwm"
sorted_df = df.sort_values(
    by="Score",
    ascending=False
)

print(sorted_df)
```

---

# 12. Basic Statistics

---

## Mean

```python id="27jlwm"
print(df["Score"].mean())
```

---

## Maximum

```python id="28jlwm"
print(df["Score"].max())
```

---

## Minimum

```python id="29jlwm"
print(df["Score"].min())
```

---

## Standard Deviation

```python id="30jlwm"
print(df["Score"].std())
```

---

# Why Statistics Matter

Statistics are essential in:

* Machine Learning
* AI preprocessing
* feature engineering
* scientific analysis

---

# 13. Handling Missing Values

---

## Checking Missing Values

```python id="31jlwm"
print(df.isnull())
```

---

## Counting Missing Values

```python id="32jlwm"
print(df.isnull().sum())
```

---

## Filling Missing Values

```python id="33jlwm"
df.fillna(0, inplace=True)
```

---

## Removing Missing Values

```python id="34jlwm"
df.dropna(inplace=True)
```

---

# Why Missing Values are Dangerous

Missing values can:

* break AI models
* create incorrect analytics
* reduce training accuracy

---

# 14. Saving Data

---

## Save as CSV

```python id="35jlwm"
df.to_csv("output.csv", index=False)
```

---

## Save as Excel

```python id="36jlwm"
df.to_excel("output.xlsx")
```

---

# 15. Real-World Applications

---

# AI and Machine Learning

Used for:

* dataset preprocessing
* feature engineering
* training data preparation

---

# Data Analytics

Used for:

* dashboards
* business intelligence
* reporting systems

---

# VLSI and Hardware Engineering

Used for:

* timing report analysis
* simulation log processing
* waveform metadata handling
* automation workflows

---

# Automation Systems

Used for:

* CSV processing
* structured logs
* monitoring systems
* reporting pipelines

---

# 16. Common Beginner Mistakes

---

## Wrong Column Name

Incorrect:

```python id="37jlwm"
print(df["score"])
```

Correct:

```python id="38jlwm"
print(df["Score"])
```

---

## Forgetting inplace=True

Incorrect:

```python id="39jlwm"
df.dropna()
```

Correct:

```python id="40jlwm"
df.dropna(inplace=True)
```

---

## Confusing loc and iloc

Remember:

| loc    | iloc      |
| ------ | --------- |
| labels | positions |

---

# 17. Best Practices

---

## Use Meaningful Column Names

Good:

```python id="41jlwm"
student_score
```

Bad:

```python id="42jlwm"
x
```

---

## Keep DataFrames Clean

Remove:

* duplicates
* missing values
* invalid entries

---

## Use Vectorized Operations

Avoid unnecessary loops.

---

## Verify Data Types

Always check:

* integers
* floats
* strings
* datetime formats

---

# 18. Interview Questions

---

## Q1. What is a DataFrame?

### Answer

A DataFrame is a 2D tabular data structure in Pandas.

---

## Q2. Difference between Series and DataFrame?

### Answer

| Series        | DataFrame        |
| ------------- | ---------------- |
| 1D            | 2D               |
| Single column | Multiple columns |

---

## Q3. Difference between loc and iloc?

### Answer

| loc         | iloc          |
| ----------- | ------------- |
| label-based | integer-based |

---

## Q4. Why are DataFrames important in AI?

### Answer

AI systems require:

* structured datasets
* preprocessing
* filtering
* feature engineering

DataFrames simplify these workflows.

---

## Q5. How does Pandas achieve performance?

### Answer

Pandas uses:

* NumPy backend
* vectorization
* optimized memory handling

---

# 19. Advanced Preview

---

## GroupBy

```python id="43jlwm"
grouped = df.groupby("Age")["Score"].mean()

print(grouped)
```

---

## Merge

```python id="44jlwm"
merged = pd.merge(df1, df2, on="ID")
```

---

## Apply Functions

```python id="45jlwm"
df["Score"] = df["Score"].apply(lambda x: x + 5)
```

---

# 20. Summary

In this notebook you learned:

* DataFrame basics
* creating DataFrames
* selecting data
* filtering
* sorting
* statistics
* missing value handling
* saving datasets
* real-world workflows

DataFrames are one of the most important foundations for:

* AI
* Machine Learning
* Data Engineering
* Analytics
* Automation

---

# Key Takeaway

DataFrames transform raw structured data into:

* analyzable information
* AI-ready datasets
* scalable processing pipelines

They are one of the most important tools in modern data-driven systems.

---

# Next Learning Path

Continue with:

```text id="46jlwm"
csv_handling.ipynb
data_cleaning.ipynb
filtering.ipynb
```

DataFrames are the bridge between:

* raw data
  and
* intelligent systems.
