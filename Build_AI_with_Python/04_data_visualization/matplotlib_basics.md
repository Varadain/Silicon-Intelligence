# Matplotlib Basics

# Overview

Matplotlib is one of the most important Python libraries for:

* Data Visualization
* Artificial Intelligence
* Machine Learning
* Scientific Computing
* Signal Processing
* Automation
* Analytics
* Robotics
* VLSI Data Analysis
* Hardware Monitoring

Matplotlib allows engineers and researchers to convert:

* raw numerical data

into:

* visual insights
* graphs
* charts
* scientific visualizations

It is the foundational visualization library used in:

* AI research
* scientific papers
* dashboards
* engineering analysis
* waveform visualization
* ML model monitoring

---

# Why Matplotlib is Important

Without visualization:

* patterns remain hidden
* debugging becomes difficult
* analytics become inefficient
* AI systems become harder to interpret

Matplotlib helps visualize:

* trends
* distributions
* correlations
* signals
* performance metrics
* neural network behavior

---

# Learning Goals

By the end of this notebook, you will understand:

* What Matplotlib is
* Why visualization matters
* Creating plots
* Line plots
* Bar charts
* Scatter plots
* Histograms
* Pie charts
* Plot customization
* Titles and labels
* Grid and legends
* Multiple plots
* Figure sizing
* Plot styling
* Saving plots
* Real-world AI applications
* Common beginner mistakes
* Best practices

---

# Installing Matplotlib

Install using pip:

```python id="mpl001"
pip install matplotlib
```

---

# Importing Matplotlib

```python id="mpl002"
import matplotlib.pyplot as plt
```

`plt` is the standard alias for Matplotlib.

---

# What is pyplot?

`pyplot` provides functions for:

* plotting graphs
* creating figures
* customizing visualizations

It works similarly to:

* drawing on a digital canvas

---

# 1. First Basic Plot

---

# Example

```python id="mpl003"
import matplotlib.pyplot as plt

x = [1, 2, 3, 4]
y = [10, 20, 15, 25]

plt.plot(x, y)

plt.show()
```

---

# Understanding the Plot

| Component | Meaning                     |
| --------- | --------------------------- |
| x-axis    | horizontal values           |
| y-axis    | vertical values             |
| line      | relationship between points |

---

# Why plt.show() is Important

`plt.show()` displays the graph.

Without it:

* graph may not appear properly.

---

# 2. Line Plot

---

# What is a Line Plot?

A line plot connects data points using lines.

Used for:

* trends
* waveform analysis
* AI training curves
* sensor monitoring
* time-series analysis

---

# Example

```python id="mpl004"
x = [1, 2, 3, 4]
y = [5, 10, 8, 15]

plt.plot(x, y)

plt.show()
```

---

# Real-World Applications

Line plots are used in:

* neural network loss curves
* RF signal analysis
* stock market trends
* IoT sensor monitoring

---

# 3. Adding Titles and Labels

---

# Example

```python id="mpl005"
plt.plot(x, y)

plt.title("Signal Analysis")
plt.xlabel("Time")
plt.ylabel("Amplitude")

plt.show()
```

---

# Why Labels Matter

Labels improve:

* readability
* interpretation
* scientific presentation quality

---

# 4. Changing Line Style

---

# Change Color

```python id="mpl006"
plt.plot(x, y, color="red")
```

---

# Change Line Width

```python id="mpl007"
plt.plot(x, y, linewidth=3)
```

---

# Change Line Style

```python id="mpl008"
plt.plot(x, y, linestyle="--")
```

---

# Common Line Styles

| Style | Meaning  |
| ----- | -------- |
| "-"   | solid    |
| "--"  | dashed   |
| ":"   | dotted   |
| "-."  | dash-dot |

---

# Add Markers

```python id="mpl009"
plt.plot(x, y, marker="o")
```

---

# Common Markers

| Marker | Shape    |
| ------ | -------- |
| o      | circle   |
| s      | square   |
| ^      | triangle |
| *      | star     |

---

# 5. Figure Size

---

# Example

```python id="mpl010"
plt.figure(figsize=(8, 5))

plt.plot(x, y)

plt.show()
```

---

# Understanding figsize

```python id="mpl011"
figsize=(width, height)
```

Measured in:

* inches

---

# Why Figure Size Matters

Important for:

* reports
* dashboards
* IEEE papers
* presentations

---

# 6. Grid and Legend

---

# Grid

```python id="mpl012"
plt.plot(x, y)

plt.grid(True)

plt.show()
```

---

# Why Grid is Useful

Grid improves:

* readability
* numerical interpretation
* debugging

---

# Legend

```python id="mpl013"
plt.plot(x, y, label="Signal")

plt.legend()

plt.show()
```

---

# Why Legends Matter

Legends help identify:

* multiple datasets
* signal types
* AI model outputs

---

# 7. Multiple Lines

---

# Example

```python id="mpl014"
x = [1, 2, 3, 4]

y1 = [1, 4, 9, 16]
y2 = [1, 2, 3, 4]

plt.plot(x, y1, label="Square")
plt.plot(x, y2, label="Linear")

plt.legend()

plt.show()
```

---

# Applications

Used for:

* comparing AI models
* comparing signals
* analytics dashboards

---

# 8. Scatter Plot

---

# What is a Scatter Plot?

Scatter plots show:

* relationships
* correlations
* clusters
* outliers

---

# Example

```python id="mpl015"
x = [1, 2, 3, 4, 5]
y = [2, 4, 5, 4, 5]

plt.scatter(x, y)

plt.show()
```

---

# Applications

Used in:

* Machine Learning
* regression analysis
* anomaly detection
* feature analysis

---

# 9. Bar Chart

---

# What is a Bar Chart?

Bar charts compare categories.

---

# Example

```python id="mpl016"
categories = ["AI", "VLSI", "Embedded"]
values = [90, 75, 85]

plt.bar(categories, values)

plt.show()
```

---

# Horizontal Bar Chart

```python id="mpl017"
plt.barh(categories, values)

plt.show()
```

---

# Applications

Used for:

* analytics
* comparisons
* ranking systems
* performance analysis

---

# 10. Histogram

---

# What is a Histogram?

Histograms show:

* data distribution
* frequency
* probability structure

---

# Example

```python id="mpl018"
data = [1, 2, 2, 3, 3, 3, 4]

plt.hist(data)

plt.show()
```

---

# Why Histograms Matter

Used in:

* statistical analysis
* AI preprocessing
* distribution analysis
* probability systems

---

# 11. Pie Chart

---

# What is a Pie Chart?

Pie charts show:

* proportions
* percentages
* category distribution

---

# Example

```python id="mpl019"
labels = ["AI", "VLSI", "Data"]
sizes = [40, 35, 25]

plt.pie(sizes, labels=labels)

plt.show()
```

---

# When to Use Pie Charts

Good for:

* small category comparisons

Avoid for:

* large datasets
* complex analytics

---

# 12. Subplots

---

# What are Subplots?

Subplots allow multiple plots in one figure.

---

# Example

```python id="mpl020"
plt.subplot(1, 2, 1)
plt.plot([1, 2, 3])

plt.subplot(1, 2, 2)
plt.plot([3, 2, 1])

plt.show()
```

---

# Understanding subplot()

```python id="mpl021"
subplot(rows, columns, position)
```

---

# Applications

Used in:

* AI dashboards
* waveform monitoring
* comparison systems

---

# 13. Saving Plots

---

# Save Figure

```python id="mpl022"
plt.plot(x, y)

plt.savefig("plot.png")
```

---

# Why Saving Matters

Used for:

* reports
* presentations
* IEEE papers
* dashboards

---

# 14. Plot Customization

---

# Background Color

```python id="mpl023"
plt.figure(facecolor="lightgray")
```

---

# Axis Limits

```python id="mpl024"
plt.xlim(0, 10)
plt.ylim(0, 20)
```

---

# Tick Labels

```python id="mpl025"
plt.xticks([1, 2, 3])
plt.yticks([0, 10, 20])
```

---

# Why Customization Matters

Customization improves:

* clarity
* readability
* professionalism

---

# 15. Real-World AI Applications

---

# Machine Learning

Visualization used for:

* loss curves
* accuracy tracking
* confusion matrices
* feature analysis

---

# Deep Learning

Used for:

* activation visualization
* tensor monitoring
* training analysis

---

# Computer Vision

Used for:

* image plotting
* segmentation analysis
* feature maps

---

# Signal Processing

Used for:

* waveform analysis
* FFT visualization
* RF monitoring

---

# VLSI and Hardware Engineering

Used for:

* timing analysis
* power monitoring
* thermal visualization
* simulation reports

---

# Scientific Computing

Used for:

* simulations
* numerical analysis
* experimental visualization

---

# 16. Common Beginner Mistakes

---

# Forgetting plt.show()

Incorrect:

```python id="mpl026"
plt.plot(x, y)
```

Correct:

```python id="mpl027"
plt.plot(x, y)

plt.show()
```

---

# Cluttered Visualizations

Avoid:

* too many colors
* excessive labels
* overlapping plots

---

# Wrong Graph Type

Examples:

* using pie chart for large datasets

---

# Missing Labels

Always include:

* title
* x-label
* y-label

---

# Forgetting Legends

Legends are important for:

* multi-line plots
* comparison systems

---

# 17. Best Practices

---

# Keep Graphs Clean

Good graphs are:

* readable
* focused
* simple

---

# Use Meaningful Titles

Good:

```python id="mpl028"
plt.title("Training Accuracy")
```

Bad:

```python id="mpl029"
plt.title("Graph")
```

---

# Choose Correct Plot Type

| Data Type     | Recommended Plot |
| ------------- | ---------------- |
| trends        | line plot        |
| categories    | bar chart        |
| distributions | histogram        |
| relationships | scatter plot     |

---

# Use Consistent Styling

Maintain:

* colors
* fonts
* spacing

for professional quality.

---

# Avoid Information Overload

Too much information reduces:

* readability
* interpretability

---

# 18. Performance Visualization

---

# AI Systems

Used for:

* model accuracy
* training loss
* inference speed

---

# Hardware Systems

Used for:

* timing reports
* thermal monitoring
* signal analysis

---

# Scientific Systems

Used for:

* simulation outputs
* numerical trends
* computational analysis

---

# 19. Interview Questions

---

# Q1. What is Matplotlib?

### Answer

Matplotlib is a Python library used for:

* data visualization
* scientific plotting
* graphical analysis

---

# Q2. Why is visualization important?

### Answer

Visualization helps:

* identify patterns
* detect anomalies
* understand trends
* communicate insights

---

# Q3. Difference between scatter plot and line plot?

### Answer

| Scatter Plot        | Line Plot        |
| ------------------- | ---------------- |
| shows relationships | shows trends     |
| individual points   | connected points |

---

# Q4. What is a histogram?

### Answer

A histogram shows:

* frequency distribution of data

---

# Q5. Why are legends important?

### Answer

Legends identify:

* datasets
* signals
* categories
* multiple plots

---

# 20. Advanced Visualization Preview

---

# Real-Time Dashboards

Used in:

* AI observability
* hardware monitoring
* analytics systems

---

# Interactive Visualization

Libraries:

* Plotly
* Dash
* Bokeh

---

# 3D Visualization

Used in:

* simulations
* tensor analysis
* scientific computing

---

# Animation

Used for:

* waveform evolution
* AI training progression
* dynamic systems

---

# 21. Typical AI Visualization Workflow

---

```text id="mpl030"
Raw Dataset
      ↓
Pandas DataFrame
      ↓
Cleaning
      ↓
Visualization
      ↓
Feature Analysis
      ↓
Machine Learning Model
      ↓
Performance Graphs
```

---

# 22. Summary

In this notebook you learned:

* Matplotlib fundamentals
* line plots
* scatter plots
* bar charts
* histograms
* pie charts
* legends
* grids
* styling
* AI visualization workflows

Matplotlib is one of the foundational libraries for:

* AI
* Machine Learning
* Analytics
* Scientific Computing
* Engineering Visualization

---

# Key Takeaway

Matplotlib transforms:

* raw numerical data

into:

* understandable visual intelligence

Good visualization improves:

* AI systems
* debugging
* analytics
* scientific communication
* engineering insight

---

# Next Learning Path

Continue with:

```text id="mpl031"
seaborn_basics.ipynb
visualization_projects/
```

Visualization is the bridge between:

* computation
  and
* human understanding.
