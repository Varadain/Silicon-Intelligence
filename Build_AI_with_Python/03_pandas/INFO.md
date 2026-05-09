# Pandas Foundations

# Overview

Pandas is one of the most powerful Python libraries for:

* Data Analysis
* Machine Learning
* Artificial Intelligence
* Data Engineering
* Financial Analysis
* Scientific Computing
* Automation
* VLSI Data Processing
* Report Analysis

Pandas is built on top of NumPy and provides high-level tools for working with structured data.

It is widely used in:

* AI pipelines
* data preprocessing
* CSV analysis
* business analytics
* automation systems
* hardware log analysis
* ML workflows

Pandas simplifies:

* reading data
* cleaning data
* filtering information
* transforming datasets
* analyzing large structured systems

---

# Why Pandas is Important

Without Pandas:

* handling structured data becomes difficult
* data preprocessing takes longer
* analytics workflows become inefficient

Pandas provides:

* fast tabular computation
* spreadsheet-like operations
* powerful filtering systems
* optimized data pipelines
* high-level data abstraction

This makes it one of the most essential libraries in:

* AI
* Data Science
* Machine Learning
* Automation Engineering

---

# Learning Goals

By the end of this module, you will understand:

* What Pandas is
* What Series and DataFrames are
* How to load datasets
* CSV handling
* Data inspection
* Data filtering
* Data cleaning
* Missing value handling
* Sorting and grouping
* Statistical operations
* Real-world AI workflows
* Performance optimization
* Data preprocessing pipelines

---

# Folder Structure

```text id="3h9b8v"
03_pandas/
│
├── README.md
├── dataframe_basics.ipynb
├── csv_handling.ipynb
├── data_cleaning.ipynb
└── filtering.ipynb
```

---

# Installing Pandas

Install Pandas using pip:

```python id="82ljq0"
pip install pandas
```

Import Pandas:

```python id="4t0jlwm"
import pandas as pd
```

`pd` is the standard alias used worldwide.

---

# What is Pandas?

Pandas is a Python library used for:

* structured data analysis
* tabular computation
* dataset manipulation

Pandas mainly provides two important data structures:

* Series
* DataFrame

---

# 1. Series

---

## What is a Series?

A Series is a one-dimensional labeled array.

It is similar to:

* a column in Excel
* a database column
* a single vector of data

---

## Creating a Series

```python id="h7r5wm"
import pandas as pd

data = pd.Series([10, 20, 30, 40])

print(data)
```

Output:

```text id="1qjlwm"
0    10
1    20
2    30
3    40
dtype: int64
```

---

# 2. DataFrame

---

## What is a DataFrame?

A DataFrame is a 2D tabular structure containing:

* rows
* columns
* labels

It is similar to:

* Excel spreadsheet
* SQL table
* CSV file

---

## Creating a DataFrame

```python id="d2zn9w"
data = {
    "Name": ["Alice", "Bob", "Charlie"],
    "Age": [21, 25, 22],
    "Score": [88, 92, 95]
}

df = pd.DataFrame(data)

print(df)
```

Output:

```text id="k7az9o"
      Name  Age  Score
0    Alice   21     88
1      Bob   25     92
2  Charlie   22     95
```

---

# Why DataFrames are Important

DataFrames are heavily used in:

* AI preprocessing
* ML datasets
* analytics systems
* automation pipelines
* CSV processing
* log analysis

---

# 3. Reading CSV Files

---

## What is CSV?

CSV stands for:

* Comma Separated Values

Used for:

* datasets
* reports
* logs
* analytics data

---

## Reading CSV

```python id="4pj0hj"
df = pd.read_csv("data.csv")

print(df)
```

---

# 4. Inspecting Data

---

## Viewing First Rows

```python id="3njlwm"
print(df.head())
```

---

## Viewing Last Rows

```python id="5o5px0"
print(df.tail())
```

---

## Checking Shape

```python id="r2vjlwm"
print(df.shape)
```

Output Example:

```text id="jlwm9u"
(100, 5)
```

Meaning:

* 100 rows
* 5 columns

---

## Column Names

```python id="b1kr9d"
print(df.columns)
```

---

## Data Types

```python id="g9l8y0"
print(df.dtypes)
```

---

# 5. Selecting Data

---

## Selecting Single Column

```python id="sz3jlwm"
print(df["Name"])
```

---

## Selecting Multiple Columns

```python id="f1uwr2"
print(df[["Name", "Score"]])
```

---

## Selecting Rows using loc

```python id="9m4jlwm"
print(df.loc[0])
```

---

## Selecting Rows using iloc

```python id="m6j3zr"
print(df.iloc[0])
```

---

# 6. Filtering Data

---

## Basic Filtering

```python id="6zjlwm"
filtered = df[df["Score"] > 90]

print(filtered)
```

---

## Multiple Conditions

```python id="2u5jlwm"
filtered = df[
    (df["Age"] > 20) &
    (df["Score"] > 90)
]

print(filtered)
```

---

# Why Filtering Matters

Filtering is essential for:

* AI preprocessing
* report analysis
* automation workflows
* hardware log parsing

---

# 7. Adding New Columns

---

## Example

```python id="y8jlwm"
df["Passed"] = df["Score"] > 50

print(df)
```

---

# 8. Updating Data

---

## Example

```python id="k2rjlwm"
df["Score"] = df["Score"] + 5

print(df)
```

---

# 9. Handling Missing Values

---

## Checking Missing Values

```python id="u1jlwm"
print(df.isnull())
```

---

## Counting Missing Values

```python id="z3jlwm"
print(df.isnull().sum())
```

---

## Filling Missing Values

```python id="n7jlwm"
df.fillna(0, inplace=True)
```

---

## Dropping Missing Values

```python id="t4jlwm"
df.dropna(inplace=True)
```

---

# Why Data Cleaning is Important

Real-world datasets often contain:

* missing values
* incorrect entries
* duplicate rows
* corrupted information

Cleaning is critical in:

* AI training
* ML preprocessing
* analytics systems

---

# 10. Sorting Data

---

## Sort by Column

```python id="r9jlwm"
sorted_df = df.sort_values(by="Score")

print(sorted_df)
```

---

## Descending Order

```python id="d7jlwm"
sorted_df = df.sort_values(
    by="Score",
    ascending=False
)

print(sorted_df)
```

---

# 11. Statistical Operations

---

## Mean

```python id="m8jlwm"
print(df["Score"].mean())
```

---

## Maximum

```python id="x4jlwm"
print(df["Score"].max())
```

---

## Minimum

```python id="p6jlwm"
print(df["Score"].min())
```

---

## Standard Deviation

```python id="a2jlwm"
print(df["Score"].std())
```

---

# 12. GroupBy Operations

---

## What is GroupBy?

GroupBy allows:

* grouping data
* aggregation
* category analysis

---

## Example

```python id="v9jlwm"
grouped = df.groupby("Age")["Score"].mean()

print(grouped)
```

---

# Why GroupBy is Important

Used in:

* business analytics
* AI preprocessing
* hardware reports
* performance analysis

---

# 13. Working with Large Datasets

---

## Checking Memory Usage

```python id="h4jlwm"
print(df.memory_usage())
```

---

## Optimizing Data Types

```python id="s8jlwm"
df["Age"] = df["Age"].astype("int32")
```

---

# 14. Exporting Data

---

## Save CSV File

```python id="w2jlwm"
df.to_csv("output.csv", index=False)
```

---

## Save Excel File

```python id="f6jlwm"
df.to_excel("output.xlsx")
```

---

# 15. Real-World AI Applications

---

## Machine Learning

Used for:

* preprocessing datasets
* feature engineering
* cleaning training data

---

## Deep Learning

Used for:

* preparing tensors
* dataset normalization
* CSV ingestion

---

## Data Engineering

Used for:

* ETL pipelines
* log processing
* structured analytics

---

## VLSI and Hardware Automation

Used for:

* timing report analysis
* simulation logs
* waveform metadata
* EDA automation

---

# 16. Common Beginner Mistakes

---

## Forgetting inplace=True

Incorrect:

```python id="q5jlwm"
df.dropna()
```

Correct:

```python id="e7jlwm"
df.dropna(inplace=True)
```

---

## Wrong Column Name

Incorrect:

```python id="j3jlwm"
print(df["score"])
```

Correct:

```python id="c9jlwm"
print(df["Score"])
```

---

## Confusing loc and iloc

| loc         | iloc          |
| ----------- | ------------- |
| label-based | integer-based |

---

# 17. Best Practices

---

## Use Meaningful Column Names

Good:

```python id="o4jlwm"
employee_salary
```

Bad:

```python id="n2jlwm"
x
```

---

## Handle Missing Values Carefully

Never ignore NaN values in production datasets.

---

## Keep DataFrames Clean

Remove:

* duplicates
* invalid rows
* corrupted data

---

## Use Vectorized Operations

Avoid unnecessary loops.

---

# 18. Performance Optimization

---

## Why Pandas is Fast

Pandas uses:

* NumPy backend
* vectorized operations
* optimized memory handling

---

## Efficient Filtering

Good:

```python id="y5jlwm"
df[df["Score"] > 90]
```

Avoid manual loops whenever possible.

---

# 19. Interview Questions

---

## Q1. Difference between Series and DataFrame?

### Answer

| Series        | DataFrame        |
| ------------- | ---------------- |
| 1D            | 2D               |
| Single column | Multiple columns |

---

## Q2. What is Pandas mainly used for?

### Answer

Pandas is used for:

* data analysis
* preprocessing
* filtering
* structured computation

---

## Q3. Difference between loc and iloc?

### Answer

| loc         | iloc          |
| ----------- | ------------- |
| label-based | integer-based |

---

## Q4. Why is Pandas important in AI?

### Answer

AI systems require:

* clean datasets
* preprocessing
* structured numerical pipelines

Pandas simplifies these workflows.

---

## Q5. How does Pandas achieve performance?

### Answer

Pandas uses:

* NumPy backend
* vectorization
* optimized memory systems

---

# 20. Advanced Pandas Concepts

---

## Merge DataFrames

```python id="u9jlwm"
merged = pd.merge(df1, df2, on="ID")
```

---

## Concatenate DataFrames

```python id="i7jlwm"
combined = pd.concat([df1, df2])
```

---

## Pivot Tables

```python id="b3jlwm"
pivot = df.pivot_table(
    values="Score",
    index="Age"
)
```

---

## Apply Functions

```python id="g6jlwm"
df["Score"] = df["Score"].apply(lambda x: x + 5)
```

---

## DateTime Processing

```python id="r5jlwm"
df["Date"] = pd.to_datetime(df["Date"])
```

---

# 21. Pandas in AI Pipelines

---

## Typical AI Workflow

```text id="t8jlwm"
CSV Data
   ↓
Pandas DataFrame
   ↓
Cleaning
   ↓
Feature Engineering
   ↓
NumPy Conversion
   ↓
Machine Learning Model
```

---

# 22. Summary

In this module you learned:

* Series
* DataFrames
* CSV handling
* filtering
* data cleaning
* grouping
* statistics
* preprocessing
* optimization
* advanced Pandas workflows

Pandas is one of the most important tools for:

* AI
* Data Science
* Machine Learning
* Automation
* Analytics
* Scientific Computing

---

# Key Takeaway

Pandas transforms raw structured data into:

* analyzable information
* AI-ready datasets
* scalable data pipelines

It is one of the foundational libraries behind:

* Machine Learning
* AI systems
* Data Engineering
* Modern analytics workflows

---

# Next Learning Path

After Pandas, continue with:

```text id="z8jlwm"
04_data_visualization/
05_statistics/
06_linear_algebra/
07_machine_learning/
```

Pandas is the bridge between:

* raw data
  and
* intelligent systems.
