# CSV Handling using Pandas

# Overview

CSV (Comma Separated Values) is one of the most widely used file formats in:

* Artificial Intelligence
* Machine Learning
* Data Science
* Data Engineering
* Analytics
* Automation
* Scientific Computing
* VLSI Report Processing
* Hardware Simulation Analysis

Most real-world datasets are stored in CSV format.

Examples:

* AI training datasets
* sensor logs
* timing reports
* financial records
* automation outputs
* analytics tables

Pandas provides powerful tools for:

* reading CSV files
* analyzing structured data
* cleaning datasets
* preprocessing information
* exporting processed data

---

# Why CSV Handling is Important

Modern systems constantly generate structured data.

Examples:

* AI datasets
* IoT logs
* FPGA simulation outputs
* business analytics reports
* automation logs

Without CSV handling:

* preprocessing becomes difficult
* data analysis becomes slower
* AI workflows become inefficient

Pandas simplifies:

* loading data
* cleaning information
* filtering records
* exporting results

---

# Learning Goals

By the end of this notebook, you will understand:

* What CSV files are
* How to read CSV files
* How to inspect datasets
* Selecting rows and columns
* Handling missing values
* Filtering CSV data
* Sorting records
* Saving processed CSV files
* Real-world AI workflows
* Common beginner mistakes
* Best practices

---

# Import Pandas

```python id="a1jlwm"
import pandas as pd
```

---

# 1. What is a CSV File?

CSV stands for:

* Comma Separated Values

A CSV file stores data in tabular form.

Example:

```text id="b2jlwm"
Name,Age,Score
Alice,21,88
Bob,25,92
Charlie,22,95
```

Each line represents:

* one row

Each comma separates:

* columns

---

# Why CSV Files are Popular

CSV files are:

* lightweight
* simple
* human-readable
* compatible with many systems

Used in:

* Excel
* databases
* AI datasets
* analytics pipelines
* automation systems

---

# 2. Reading CSV Files

---

# Basic CSV Reading

```python id="c3jlwm"
df = pd.read_csv("data.csv")

print(df)
```

---

# What Happens Internally?

Pandas:

1. opens file
2. reads rows
3. detects columns
4. creates DataFrame

---

# Example Output

```text id="d4jlwm"
      Name  Age  Score
0    Alice   21     88
1      Bob   25     92
2  Charlie   22     95
```

---

# 3. Viewing Dataset Information

---

# First 5 Rows

```python id="e5jlwm"
print(df.head())
```

---

# Last 5 Rows

```python id="f6jlwm"
print(df.tail())
```

---

# Dataset Shape

```python id="g7jlwm"
print(df.shape)
```

Output Example:

```text id="h8jlwm"
(100, 5)
```

Meaning:

* 100 rows
* 5 columns

---

# Column Names

```python id="i9jlwm"
print(df.columns)
```

---

# Data Types

```python id="j0jlwm"
print(df.dtypes)
```

---

# Dataset Information

```python id="k1jlwm"
print(df.info())
```

Shows:

* total rows
* columns
* datatypes
* memory usage

---

# Why Dataset Inspection Matters

Inspection helps in:

* debugging
* preprocessing
* AI training preparation
* analytics validation

---

# 4. Selecting Columns

---

# Single Column

```python id="l2jlwm"
print(df["Name"])
```

---

# Multiple Columns

```python id="m3jlwm"
print(df[["Name", "Score"]])
```

---

# 5. Selecting Rows

---

# Using loc

```python id="n4jlwm"
print(df.loc[0])
```

---

# Using iloc

```python id="o5jlwm"
print(df.iloc[0])
```

---

# Difference Between loc and iloc

| loc         | iloc          |
| ----------- | ------------- |
| label-based | integer-based |

---

# 6. Filtering CSV Data

---

# Basic Filtering

```python id="p6jlwm"
filtered = df[df["Score"] > 90]

print(filtered)
```

---

# Multiple Conditions

```python id="q7jlwm"
filtered = df[
    (df["Age"] > 20) &
    (df["Score"] > 90)
]

print(filtered)
```

---

# Why Filtering Matters

Filtering is heavily used in:

* AI preprocessing
* report analysis
* analytics systems
* automation pipelines

---

# 7. Handling Missing Values

---

# What are Missing Values?

Sometimes datasets contain:

* empty cells
* incomplete rows
* corrupted information

Example:

```text id="r8jlwm"
Name,Age,Score
Alice,21,88
Bob,,92
Charlie,22,
```

---

# Detect Missing Values

```python id="s9jlwm"
print(df.isnull())
```

---

# Count Missing Values

```python id="t0jlwm"
print(df.isnull().sum())
```

---

# Fill Missing Values

```python id="u1jlwm"
df.fillna(0, inplace=True)
```

---

# Remove Missing Values

```python id="v2jlwm"
df.dropna(inplace=True)
```

---

# Why Missing Values are Dangerous

Missing values can:

* break AI models
* reduce accuracy
* create incorrect analytics
* corrupt preprocessing

---

# 8. Updating CSV Data

---

# Add New Column

```python id="w3jlwm"
df["Passed"] = df["Score"] > 50
```

---

# Modify Existing Column

```python id="x4jlwm"
df["Score"] = df["Score"] + 5
```

---

# Update Specific Cell

```python id="y5jlwm"
df.loc[0, "Score"] = 100
```

---

# 9. Sorting Data

---

# Ascending Order

```python id="z6jlwm"
sorted_df = df.sort_values(by="Score")

print(sorted_df)
```

---

# Descending Order

```python id="a7jlwm"
sorted_df = df.sort_values(
    by="Score",
    ascending=False
)

print(sorted_df)
```

---

# 10. Statistical Operations

---

# Mean

```python id="b8jlwm"
print(df["Score"].mean())
```

---

# Maximum

```python id="c9jlwm"
print(df["Score"].max())
```

---

# Minimum

```python id="d0jlwm"
print(df["Score"].min())
```

---

# Standard Deviation

```python id="e1jlwm"
print(df["Score"].std())
```

---

# Why Statistics Matter

Statistics are important in:

* AI preprocessing
* feature engineering
* scientific analysis
* automation systems

---

# 11. Saving Processed CSV Files

---

# Save CSV

```python id="f2jlwm"
df.to_csv("processed_data.csv", index=False)
```

---

# Why index=False?

Without `index=False`,
Pandas also saves row indices.

---

# Save Excel File

```python id="g3jlwm"
df.to_excel("output.xlsx")
```

---

# 12. Reading Large CSV Files

---

# Problem with Large Files

Large datasets may:

* consume memory
* slow down processing

---

# Reading Partial Data

```python id="h4jlwm"
df = pd.read_csv("data.csv", nrows=100)
```

---

# Reading Specific Columns

```python id="i5jlwm"
df = pd.read_csv(
    "data.csv",
    usecols=["Name", "Score"]
)
```

---

# 13. Real-World AI Applications

---

# Machine Learning

CSV files are used for:

* training datasets
* feature engineering
* preprocessing

---

# Deep Learning

Used for:

* tensor preparation
* structured metadata
* dataset ingestion

---

# Data Engineering

Used for:

* ETL pipelines
* analytics systems
* reporting frameworks

---

# VLSI and Hardware Engineering

Used for:

* timing reports
* simulation logs
* waveform metadata
* EDA automation

---

# Automation Systems

Used for:

* structured logs
* monitoring systems
* reporting automation

---

# 14. Common Beginner Mistakes

---

# Wrong File Path

Incorrect:

```python id="j6jlwm"
pd.read_csv("wrong_file.csv")
```

Causes:

* FileNotFoundError

---

# Forgetting Quotes Around Column Names

Incorrect:

```python id="k7jlwm"
df[Score]
```

Correct:

```python id="l8jlwm"
df["Score"]
```

---

# Ignoring Missing Values

Missing values can silently break:

* ML pipelines
* analytics systems
* automation workflows

---

# Confusing loc and iloc

| loc    | iloc      |
| ------ | --------- |
| labels | positions |

---

# 15. Best Practices

---

# Use Meaningful Column Names

Good:

```python id="m9jlwm"
employee_salary
```

Bad:

```python id="n0jlwm"
x
```

---

# Always Inspect Data First

Use:

* head()
* info()
* shape()

before processing.

---

# Handle Missing Values Carefully

Never ignore NaN values in production systems.

---

# Keep DataFrames Clean

Remove:

* duplicates
* invalid rows
* corrupted entries

---

# Use Vectorized Operations

Avoid unnecessary loops.

---

# 16. Performance Optimization

---

# Why Pandas is Fast

Pandas uses:

* NumPy backend
* vectorized operations
* optimized memory handling

---

# Efficient Filtering

Good:

```python id="o1jlwm"
df[df["Score"] > 90]
```

Avoid manual iteration whenever possible.

---

# 17. Interview Questions

---

# Q1. What is a CSV file?

### Answer

CSV stands for:

* Comma Separated Values

Used for storing structured tabular data.

---

# Q2. How do you read a CSV file in Pandas?

### Answer

```python id="p2jlwm"
pd.read_csv("data.csv")
```

---

# Q3. Why are CSV files important in AI?

### Answer

AI systems require:

* structured datasets
* preprocessing pipelines
* tabular numerical data

CSV is one of the most common formats.

---

# Q4. Difference between loc and iloc?

### Answer

| loc         | iloc          |
| ----------- | ------------- |
| label-based | integer-based |

---

# Q5. How does Pandas achieve high performance?

### Answer

Pandas uses:

* NumPy backend
* vectorization
* optimized memory systems

---

# 18. Advanced Preview

---

# GroupBy

```python id="q3jlwm"
grouped = df.groupby("Age")["Score"].mean()
```

---

# Merge

```python id="r4jlwm"
merged = pd.merge(df1, df2, on="ID")
```

---

# Apply Functions

```python id="s5jlwm"
df["Score"] = df["Score"].apply(lambda x: x + 5)
```

---

# DateTime Processing

```python id="t6jlwm"
df["Date"] = pd.to_datetime(df["Date"])
```

---

# 19. Typical AI Data Workflow

---

```text id="u7jlwm"
CSV Dataset
     ↓
Pandas DataFrame
     ↓
Cleaning
     ↓
Filtering
     ↓
Feature Engineering
     ↓
Machine Learning Model
```

---

# 20. Summary

In this notebook you learned:

* CSV fundamentals
* reading CSV files
* dataset inspection
* filtering
* sorting
* missing value handling
* statistics
* exporting data
* real-world AI workflows

CSV handling is one of the most important skills for:

* AI
* Machine Learning
* Data Science
* Automation
* Analytics
* Scientific Computing

---

# Key Takeaway

CSV files are the bridge between:

* raw structured data
  and
* intelligent systems

Pandas transforms CSV datasets into:

* analyzable information
* AI-ready pipelines
* scalable processing systems

---

# Next Learning Path

Continue with:

```text id="v8jlwm"
data_cleaning.ipynb
filtering.ipynb
```

Strong CSV handling skills are essential for:

* AI engineers
* automation engineers
* data scientists
* VLSI analytics workflows
