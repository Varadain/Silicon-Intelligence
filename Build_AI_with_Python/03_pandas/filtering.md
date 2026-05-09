# Data Filtering using Pandas

# Overview

Filtering is one of the most important operations in:

* Artificial Intelligence
* Machine Learning
* Data Science
* Analytics
* Automation
* Scientific Computing
* Data Engineering
* VLSI Report Analysis
* Hardware Simulation Processing

Real-world datasets often contain:

* thousands of rows
* unnecessary information
* noisy data
* irrelevant records

Filtering helps extract:

* useful information
* important patterns
* targeted datasets
* meaningful insights

Pandas provides powerful filtering tools for:

* row selection
* column selection
* conditional filtering
* logical operations
* query-based filtering

---

# Why Filtering is Important

Modern systems process massive datasets.

Examples:

* AI training datasets
* timing reports
* sensor logs
* automation records
* simulation outputs
* customer analytics

Without filtering:

* analysis becomes difficult
* preprocessing becomes inefficient
* AI models receive noisy data

Filtering helps:

* reduce noise
* improve accuracy
* simplify analysis
* optimize preprocessing

---

# Learning Goals

By the end of this notebook, you will understand:

* What filtering is
* Selecting rows and columns
* Conditional filtering
* Multiple condition filtering
* loc and iloc
* Query filtering
* String filtering
* Filtering missing values
* Sorting filtered data
* Real-world AI applications
* Common beginner mistakes
* Best practices

---

# Import Pandas

```python id="a1flt"
import pandas as pd
```

---

# 1. Creating Sample Dataset

```python id="b2flt"
data = {
    "Name": ["Alice", "Bob", "Charlie", "David", "Eva"],
    "Age": [21, 25, 22, 28, 24],
    "Score": [88, 92, 95, 70, 85],
    "Department": [
        "AI",
        "VLSI",
        "AI",
        "Embedded",
        "Data"
    ]
}

df = pd.DataFrame(data)

print(df)
```

---

# Output

```text id="c3flt"
      Name  Age  Score Department
0    Alice   21     88         AI
1      Bob   25     92       VLSI
2  Charlie   22     95         AI
3    David   28     70   Embedded
4      Eva   24     85       Data
```

---

# 2. Selecting Columns

---

# Single Column

```python id="d4flt"
print(df["Name"])
```

---

# Multiple Columns

```python id="e5flt"
print(df[["Name", "Score"]])
```

---

# Why Column Selection Matters

Used for:

* feature engineering
* analytics
* AI preprocessing
* report generation

---

# 3. Selecting Rows using loc

---

# What is loc?

`loc` selects rows using:

* labels

---

# Example

```python id="f6flt"
print(df.loc[0])
```

---

# Multiple Rows

```python id="g7flt"
print(df.loc[0:2])
```

---

# Selecting Specific Columns

```python id="h8flt"
print(df.loc[0:2, ["Name", "Score"]])
```

---

# 4. Selecting Rows using iloc

---

# What is iloc?

`iloc` selects rows using:

* integer positions

---

# Example

```python id="i9flt"
print(df.iloc[0])
```

---

# Multiple Rows

```python id="j0flt"
print(df.iloc[0:3])
```

---

# Selecting Specific Columns

```python id="k1flt"
print(df.iloc[0:3, 0:2])
```

---

# Difference Between loc and iloc

| loc         | iloc          |
| ----------- | ------------- |
| label-based | integer-based |

---

# 5. Basic Conditional Filtering

---

# Filtering by Condition

```python id="l2flt"
filtered = df[df["Score"] > 90]

print(filtered)
```

---

# Output

```text id="m3flt"
      Name  Age  Score Department
1      Bob   25     92       VLSI
2  Charlie   22     95         AI
```

---

# How Filtering Works

Pandas checks:

* every row

Condition:

* Score > 90

Rows satisfying condition:

* are returned

---

# 6. Multiple Conditions

---

# AND Condition

```python id="n4flt"
filtered = df[
    (df["Age"] > 22) &
    (df["Score"] > 80)
]

print(filtered)
```

---

# OR Condition

```python id="o5flt"
filtered = df[
    (df["Department"] == "AI") |
    (df["Department"] == "Data")
]

print(filtered)
```

---

# Why Logical Filtering Matters

Used in:

* AI preprocessing
* analytics pipelines
* automation systems
* dataset segmentation

---

# 7. Filtering String Data

---

# Exact Match

```python id="p6flt"
filtered = df[df["Department"] == "AI"]

print(filtered)
```

---

# String Contains

```python id="q7flt"
filtered = df[
    df["Department"].str.contains("AI")
]

print(filtered)
```

---

# String Starts With

```python id="r8flt"
filtered = df[
    df["Name"].str.startswith("A")
]

print(filtered)
```

---

# String Ends With

```python id="s9flt"
filtered = df[
    df["Name"].str.endswith("a")
]

print(filtered)
```

---

# Why String Filtering Matters

Used in:

* NLP preprocessing
* automation systems
* search pipelines
* analytics workflows

---

# 8. Filtering Missing Values

---

# Detect Missing Values

```python id="t0flt"
print(df.isnull())
```

---

# Rows with Missing Values

```python id="u1flt"
filtered = df[df["Score"].isnull()]
```

---

# Rows without Missing Values

```python id="v2flt"
filtered = df[df["Score"].notnull()]
```

---

# Why Missing Value Filtering Matters

Used in:

* AI preprocessing
* dataset validation
* automation systems

---

# 9. Query Method

---

# What is query()?

`query()` provides SQL-like filtering.

---

# Example

```python id="w3flt"
filtered = df.query("Score > 90")

print(filtered)
```

---

# Multiple Conditions

```python id="x4flt"
filtered = df.query(
    "Age > 22 and Score > 80"
)

print(filtered)
```

---

# Why query() is Useful

Benefits:

* readable syntax
* cleaner conditions
* SQL-style workflows

---

# 10. Sorting Filtered Data

---

# Ascending Order

```python id="y5flt"
filtered = df.sort_values(by="Score")

print(filtered)
```

---

# Descending Order

```python id="z6flt"
filtered = df.sort_values(
    by="Score",
    ascending=False
)

print(filtered)
```

---

# Why Sorting Matters

Sorting helps:

* ranking systems
* AI analysis
* report generation
* recommendation systems

---

# 11. Filtering Specific Value Ranges

---

# Using Between

```python id="a7flt"
filtered = df[
    df["Score"].between(80, 90)
]

print(filtered)
```

---

# Why Range Filtering Matters

Used in:

* analytics dashboards
* AI preprocessing
* signal analysis
* automation systems

---

# 12. Real-World AI Applications

---

# Machine Learning

Filtering is used for:

* feature selection
* class separation
* training dataset preparation

---

# Deep Learning

Used for:

* tensor preprocessing
* data segmentation
* label filtering

---

# Data Engineering

Used for:

* ETL pipelines
* analytics systems
* structured processing

---

# VLSI and Hardware Engineering

Used for:

* timing report filtering
* simulation analysis
* waveform processing
* EDA automation

---

# Automation Systems

Used for:

* log filtering
* monitoring systems
* reporting frameworks

---

# 13. Common Beginner Mistakes

---

# Forgetting Parentheses

Incorrect:

```python id="b8flt"
df[df["Age"] > 20 & df["Score"] > 80]
```

Correct:

```python id="c9flt"
df[
    (df["Age"] > 20) &
    (df["Score"] > 80)
]
```

---

# Using and Instead of &

Incorrect:

```python id="d0flt"
df[
    (df["Age"] > 20) and
    (df["Score"] > 80)
]
```

Correct:

```python id="e1flt"
df[
    (df["Age"] > 20) &
    (df["Score"] > 80)
]
```

---

# Confusing loc and iloc

| loc    | iloc      |
| ------ | --------- |
| labels | positions |

---

# Forgetting Quotes Around Column Names

Incorrect:

```python id="f2flt"
df[Score]
```

Correct:

```python id="g3flt"
df["Score"]
```

---

# 14. Best Practices

---

# Use Meaningful Conditions

Good:

```python id="h4flt"
df[df["Score"] > 90]
```

Bad:

```python id="i5flt"
df[df["x"] > 90]
```

---

# Keep Filtering Readable

Use:

* line breaks
* proper spacing
* logical grouping

---

# Use query() for Complex Conditions

Improves readability.

---

# Validate Dataset Before Filtering

Always inspect:

* columns
* datatypes
* missing values

---

# Avoid Unnecessary Loops

Use vectorized filtering instead.

---

# 15. Performance Optimization

---

# Why Pandas Filtering is Fast

Pandas uses:

* NumPy backend
* vectorized operations
* optimized memory systems

---

# Efficient Filtering

Good:

```python id="j6flt"
df[df["Score"] > 90]
```

Avoid manual iteration whenever possible.

---

# 16. Interview Questions

---

# Q1. What is filtering in Pandas?

### Answer

Filtering selects specific rows or columns based on conditions.

---

# Q2. Difference between loc and iloc?

### Answer

| loc         | iloc          |
| ----------- | ------------- |
| label-based | integer-based |

---

# Q3. Why is filtering important in AI?

### Answer

Filtering helps:

* remove noise
* select relevant data
* improve preprocessing
* optimize model training

---

# Q4. Difference between & and and in Pandas?

### Answer

| &                             | and                     |
| ----------------------------- | ----------------------- |
| element-wise logical operator | Python logical operator |

Pandas filtering requires:

* &
* |

---

# Q5. What is query()?

### Answer

`query()` provides SQL-like filtering syntax for DataFrames.

---

# 17. Typical AI Filtering Workflow

---

```text id="k7flt"
Raw Dataset
      ↓
Inspect Columns
      ↓
Filter Relevant Rows
      ↓
Remove Noise
      ↓
Feature Selection
      ↓
AI-Ready Dataset
```

---

# 18. Summary

In this notebook you learned:

* row filtering
* column filtering
* conditional filtering
* logical operations
* query filtering
* string filtering
* missing value filtering
* sorting workflows

Filtering is one of the most important foundations for:

* AI
* Machine Learning
* Data Science
* Automation
* Analytics

---

# Key Takeaway

Filtering transforms large raw datasets into:

* targeted information
* AI-ready datasets
* meaningful analytics
* optimized preprocessing pipelines

Efficient filtering is critical for:

* intelligent systems
* scalable analytics
* high-performance automation

---

# Next Learning Path

Continue with:

```text id="l8flt"
04_data_visualization/
```

Filtering is the bridge between:

* raw information
  and
* intelligent decision systems.
