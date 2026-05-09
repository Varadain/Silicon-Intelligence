# Data Cleaning using Pandas

# Overview

Data cleaning is one of the most important steps in:

* Artificial Intelligence
* Machine Learning
* Data Science
* Analytics
* Automation
* Scientific Computing
* Data Engineering
* VLSI Report Processing
* Hardware Log Analysis

Real-world datasets are often:

* incomplete
* inconsistent
* duplicated
* noisy
* corrupted

Before training AI models or performing analysis, datasets must be cleaned properly.

Data cleaning improves:

* model accuracy
* analytics reliability
* automation quality
* system performance

Pandas provides powerful tools for:

* handling missing values
* removing duplicates
* fixing incorrect data
* formatting datasets
* preprocessing information

---

# Why Data Cleaning is Important

Bad data causes:

* incorrect AI predictions
* failed automation pipelines
* inaccurate analytics
* unstable machine learning models

Example problems:

* empty cells
* duplicate records
* invalid numbers
* inconsistent formatting
* corrupted timestamps

Without cleaning:

* AI systems become unreliable
* preprocessing fails
* training accuracy decreases

---

# Learning Goals

By the end of this notebook, you will understand:

* What dirty data is
* Detecting missing values
* Filling missing values
* Removing missing values
* Removing duplicate rows
* Handling incorrect data
* String cleaning
* Data type conversion
* Outlier detection basics
* Data normalization basics
* Real-world AI workflows
* Common beginner mistakes
* Best practices

---

# Import Pandas

```python id="a1cln"
import pandas as pd
```

---

# 1. What is Dirty Data?

Dirty data refers to:

* incomplete data
* incorrect values
* duplicate entries
* inconsistent formatting

Example:

```text id="b2cln"
Name,Age,Score
Alice,21,88
Bob,,92
Charlie,22,
Bob,,92
```

Problems:

* missing values
* duplicate row
* incomplete information

---

# Why Dirty Data is Dangerous

Dirty data can:

* reduce AI accuracy
* create biased models
* break analytics pipelines
* corrupt automation systems

---

# 2. Creating Sample Dataset

```python id="c3cln"
data = {
    "Name": ["Alice", "Bob", "Charlie", "Bob"],
    "Age": [21, None, 22, None],
    "Score": [88, 92, None, 92]
}

df = pd.DataFrame(data)

print(df)
```

---

# Output

```text id="d4cln"
      Name   Age  Score
0    Alice  21.0   88.0
1      Bob   NaN   92.0
2  Charlie  22.0    NaN
3      Bob   NaN   92.0
```

---

# 3. Understanding Missing Values

---

# What is NaN?

NaN means:

* Not a Number

It represents:

* missing or undefined data

---

# Detect Missing Values

```python id="e5cln"
print(df.isnull())
```

---

# Count Missing Values

```python id="f6cln"
print(df.isnull().sum())
```

Output Example:

```text id="g7cln"
Name     0
Age      2
Score    1
dtype: int64
```

---

# Why Missing Values Matter

Missing values can:

* confuse AI models
* reduce training quality
* create incorrect analytics

---

# 4. Filling Missing Values

---

# Fill with Constant Value

```python id="h8cln"
df.fillna(0, inplace=True)

print(df)
```

---

# Fill with Mean

```python id="i9cln"
df["Age"].fillna(
    df["Age"].mean(),
    inplace=True
)
```

---

# Fill with Median

```python id="j0cln"
df["Score"].fillna(
    df["Score"].median(),
    inplace=True
)
```

---

# Why Mean and Median are Used

Used for:

* preserving statistical distribution
* maintaining dataset consistency
* improving ML preprocessing

---

# 5. Removing Missing Values

---

# Remove Rows with Missing Values

```python id="k1cln"
df.dropna(inplace=True)
```

---

# Remove Columns with Missing Values

```python id="l2cln"
df.dropna(axis=1, inplace=True)
```

---

# Understanding axis

| axis | Meaning |
| ---- | ------- |
| 0    | rows    |
| 1    | columns |

---

# When to Remove Missing Data

Use carefully because:

* important information may be lost

---

# 6. Removing Duplicate Rows

---

# Detect Duplicates

```python id="m3cln"
print(df.duplicated())
```

---

# Remove Duplicates

```python id="n4cln"
df.drop_duplicates(inplace=True)
```

---

# Why Duplicate Data is Dangerous

Duplicates can:

* bias AI models
* distort statistics
* increase storage unnecessarily

---

# 7. Cleaning String Data

---

# Problem Example

```python id="o5cln"
data = {
    "Name": [" Alice ", "BOB", "charlie"]
}

df = pd.DataFrame(data)
```

---

# Remove Extra Spaces

```python id="p6cln"
df["Name"] = df["Name"].str.strip()
```

---

# Convert to Lowercase

```python id="q7cln"
df["Name"] = df["Name"].str.lower()
```

---

# Convert to Uppercase

```python id="r8cln"
df["Name"] = df["Name"].str.upper()
```

---

# Why String Cleaning Matters

Used in:

* NLP systems
* search systems
* AI preprocessing
* automation workflows

---

# 8. Replacing Incorrect Values

---

# Example

```python id="s9cln"
df["Department"] = [
    "HR",
    "hr",
    "Human Resources"
]
```

---

# Replace Values

```python id="t0cln"
df["Department"] = df[
    "Department"
].replace(
    {
        "hr": "HR",
        "Human Resources": "HR"
    }
)
```

---

# Why Standardization Matters

Standardization improves:

* consistency
* filtering
* grouping
* ML preprocessing

---

# 9. Changing Data Types

---

# Check Data Types

```python id="u1cln"
print(df.dtypes)
```

---

# Convert Data Type

```python id="v2cln"
df["Age"] = df["Age"].astype("int32")
```

---

# Convert to Datetime

```python id="w3cln"
df["Date"] = pd.to_datetime(df["Date"])
```

---

# Why Data Types Matter

Correct datatypes improve:

* memory efficiency
* performance
* numerical computation
* ML preprocessing

---

# 10. Handling Outliers

---

# What are Outliers?

Outliers are:

* unusually large or small values

Example:

* salary = 10000000
  in normal dataset

---

# Detecting Outliers

```python id="x4cln"
print(df.describe())
```

---

# Why Outliers Matter

Outliers can:

* distort ML models
* create unstable predictions
* affect statistics

---

# 11. Data Normalization Basics

---

# Why Normalize Data?

Different scales can affect:

* ML training
* optimization
* neural network performance

---

# Example

```python id="y5cln"
df["Score"] = (
    df["Score"] - df["Score"].mean()
) / df["Score"].std()
```

---

# Used in

* Machine Learning
* Deep Learning
* AI preprocessing

---

# 12. Real-World AI Applications

---

# Machine Learning

Used for:

* preprocessing datasets
* feature cleaning
* removing noisy data

---

# Deep Learning

Used for:

* tensor preparation
* normalization
* structured training pipelines

---

# Data Engineering

Used for:

* ETL pipelines
* large-scale preprocessing
* analytics systems

---

# VLSI and Hardware Engineering

Used for:

* timing report cleaning
* simulation logs
* waveform metadata
* EDA automation

---

# Automation Systems

Used for:

* monitoring systems
* reporting frameworks
* structured logs

---

# 13. Common Beginner Mistakes

---

# Ignoring Missing Values

Dangerous because:

* ML models may fail
* analytics become inaccurate

---

# Removing Too Much Data

Incorrect:

```python id="z6cln"
df.dropna(inplace=True)
```

without checking impact.

---

# Wrong Data Type Conversion

Incorrect:

```python id="a7cln"
df["Age"] = df["Age"].astype("int")
```

when missing values exist.

---

# Forgetting inplace=True

Incorrect:

```python id="b8cln"
df.drop_duplicates()
```

Correct:

```python id="c9cln"
df.drop_duplicates(inplace=True)
```

---

# 14. Best Practices

---

# Always Inspect Data First

Use:

* head()
* info()
* describe()
* isnull()

---

# Handle Missing Values Carefully

Choose:

* fill
  OR
* remove

based on dataset importance.

---

# Standardize Text Data

Ensure:

* consistent formatting
* consistent labels

---

# Validate Data Types

Always verify:

* integers
* floats
* datetime
* categorical data

---

# Avoid Unnecessary Data Loss

Never remove rows blindly.

---

# 15. Performance Optimization

---

# Why Pandas is Fast

Pandas uses:

* NumPy backend
* vectorized execution
* optimized memory systems

---

# Efficient Cleaning

Good:

```python id="d0cln"
df.fillna(0)
```

Avoid manual loops whenever possible.

---

# 16. Interview Questions

---

# Q1. What is data cleaning?

### Answer

Data cleaning is the process of:

* fixing
* removing
* correcting
* preprocessing dirty data

---

# Q2. What are missing values?

### Answer

Missing values represent:

* incomplete information

Usually represented as:

* NaN

---

# Q3. Why are duplicates dangerous?

### Answer

Duplicates can:

* bias AI models
* distort analytics
* increase storage unnecessarily

---

# Q4. Difference between fillna() and dropna()?

### Answer

| fillna()             | dropna()             |
| -------------------- | -------------------- |
| fills missing values | removes missing data |

---

# Q5. Why is data cleaning important in AI?

### Answer

AI systems require:

* accurate
* clean
* structured
* consistent data

Dirty data reduces model quality.

---

# 17. Typical AI Data Cleaning Pipeline

---

```text id="e1cln"
Raw Dataset
      ↓
Inspect Data
      ↓
Handle Missing Values
      ↓
Remove Duplicates
      ↓
Fix Incorrect Data
      ↓
Normalize Features
      ↓
AI-Ready Dataset
```

---

# 18. Summary

In this notebook you learned:

* missing value handling
* duplicate removal
* string cleaning
* datatype conversion
* normalization basics
* outlier handling
* AI preprocessing workflows

Data cleaning is one of the most important foundations for:

* AI
* Machine Learning
* Data Science
* Analytics
* Automation

---

# Key Takeaway

Real-world data is rarely clean.

Pandas transforms:

* noisy datasets
  into:
* reliable AI-ready information

Data cleaning is one of the most critical stages in:

* intelligent systems
* analytics pipelines
* machine learning workflows

---

# Next Learning Path

Continue with:

```text id="f2cln"
filtering.ipynb
```

Clean data creates:

* accurate AI systems
* reliable analytics
* scalable automation pipelines
