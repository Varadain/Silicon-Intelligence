# NumPy Arrays Fundamentals

# Introduction

Arrays are the foundation of numerical computing in Python.

In Machine Learning, AI, Robotics, Scientific Computing, and VLSI Automation, arrays are used everywhere.

NumPy arrays provide:

* fast computation
* optimized memory usage
* vectorized operations
* mathematical processing capabilities

This notebook introduces the fundamentals of NumPy arrays from beginner to intermediate level.

---

# Learning Objectives

By the end of this notebook, you will understand:

* What arrays are
* Why NumPy arrays are important
* Difference between Python lists and NumPy arrays
* How to create arrays
* Array dimensions
* Array shapes
* Indexing and slicing
* Array operations
* Memory efficiency concepts
* Real-world applications

---

# Importing NumPy

```python id="ktj7qg"
import numpy as np
```

`np` is the standard alias for NumPy.

---

# What is an Array?

An array is a collection of elements stored in continuous memory locations.

Arrays are:

* ordered
* indexed
* fast
* efficient for numerical operations

---

# Why Arrays are Important

Arrays are used in:

* Machine Learning
* Deep Learning
* Image Processing
* Computer Vision
* Signal Processing
* Robotics
* VLSI Automation
* FPGA Research
* Scientific Simulation

Without arrays:

* numerical computation becomes slower
* memory usage increases
* AI systems become inefficient

---

# Python List vs NumPy Array

---

# Python List Example

```python id="6dzn2v"
numbers = [1, 2, 3, 4, 5]

print(numbers)
```

Output:

```text id="8p7dvm"
[1, 2, 3, 4, 5]
```

---

# NumPy Array Example

```python id="x63xru"
arr = np.array([1, 2, 3, 4, 5])

print(arr)
```

Output:

```text id="5p5r8g"
[1 2 3 4 5]
```

---

# Why NumPy Arrays are Faster

NumPy arrays are faster because:

* elements are stored continuously in memory
* operations use optimized C backend
* vectorized execution reduces Python overhead

This makes NumPy ideal for:

* large datasets
* AI computation
* mathematical processing
* simulations

---

# Creating Arrays

---

# 1D Array

```python id="g5az6i"
arr = np.array([10, 20, 30, 40])

print(arr)
```

---

# 2D Array

```python id="xx6c8t"
matrix = np.array([
    [1, 2],
    [3, 4]
])

print(matrix)
```

Output:

```text id="j49zri"
[[1 2]
 [3 4]]
```

---

# 3D Array

```python id="6ojw3g"
tensor = np.array([
    [
        [1, 2],
        [3, 4]
    ],
    [
        [5, 6],
        [7, 8]
    ]
])

print(tensor)
```

---

# Understanding Dimensions

| Dimension | Description  |
| --------- | ------------ |
| 1D        | Linear array |
| 2D        | Matrix       |
| 3D        | Tensor       |

---

# Checking Array Dimensions

```python id="7m1m1q"
arr = np.array([1, 2, 3])

print(arr.ndim)
```

Output:

```text id="p89cxh"
1
```

---

# Example with 2D Array

```python id="cxyv1v"
matrix = np.array([
    [1, 2],
    [3, 4]
])

print(matrix.ndim)
```

Output:

```text id="6y2hwt"
2
```

---

# Understanding Shape

Shape tells:

* number of rows
* number of columns

---

# Shape Example

```python id="l4b8zr"
matrix = np.array([
    [1, 2, 3],
    [4, 5, 6]
])

print(matrix.shape)
```

Output:

```text id="7m6v2m"
(2, 3)
```

Meaning:

* 2 rows
* 3 columns

---

# Checking Data Type

```python id="whiww6"
arr = np.array([1, 2, 3])

print(arr.dtype)
```

Output:

```text id="y2x2yq"
int64
```

---

# Common NumPy Data Types

| Data Type  | Meaning        |
| ---------- | -------------- |
| int32      | Integer        |
| float64    | Floating point |
| bool       | Boolean        |
| complex128 | Complex number |

---

# Creating Arrays with Specific Data Types

```python id="vvmc1s"
arr = np.array([1, 2, 3], dtype=float)

print(arr)
```

Output:

```text id="mjlwm4"
[1. 2. 3.]
```

---

# Creating Special Arrays

---

# Array of Zeros

```python id="67p94s"
zeros = np.zeros((2, 3))

print(zeros)
```

Output:

```text id="5m91q1"
[[0. 0. 0.]
 [0. 0. 0.]]
```

---

# Array of Ones

```python id="9q1y94"
ones = np.ones((3, 3))

print(ones)
```

---

# Identity Matrix

```python id="u5o7yz"
identity = np.eye(3)

print(identity)
```

Output:

```text id="gb80vj"
[[1. 0. 0.]
 [0. 1. 0.]
 [0. 0. 1.]]
```

Used in:

* Linear Algebra
* AI Systems
* Matrix Transformations

---

# Array Indexing

---

# Accessing Single Element

```python id="k3n8zq"
arr = np.array([10, 20, 30])

print(arr[0])
```

Output:

```text id="0a7olp"
10
```

---

# Negative Indexing

```python id="ycjlwm"
print(arr[-1])
```

Output:

```text id="0n4n8r"
30
```

---

# 2D Indexing

```python id="6crn0r"
matrix = np.array([
    [1, 2],
    [3, 4]
])

print(matrix[1][0])
```

Output:

```text id="n7hj2r"
3
```

---

# Array Slicing

---

# Basic Slicing

```python id="a0gr2q"
arr = np.array([1, 2, 3, 4, 5])

print(arr[1:4])
```

Output:

```text id="5rrm4h"
[2 3 4]
```

---

# Step Slicing

```python id="0l97h4"
print(arr[::2])
```

Output:

```text id="vgnxj5"
[1 3 5]
```

---

# Reverse Array

```python id="spyrjo"
print(arr[::-1])
```

Output:

```text id="znvh7i"
[5 4 3 2 1]
```

---

# Array Operations

---

# Addition

```python id="ksd8wv"
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

print(a + b)
```

Output:

```text id="y9hbx4"
[5 7 9]
```

---

# Subtraction

```python id="xdvppg"
print(a - b)
```

Output:

```text id="icf7zw"
[-3 -3 -3]
```

---

# Multiplication

```python id="jlwm9u"
print(a * b)
```

Output:

```text id="0x9mhk"
[ 4 10 18]
```

---

# Division

```python id="jfb1by"
print(a / b)
```

---

# Scalar Operations

```python id="wvobm0"
arr = np.array([1, 2, 3])

print(arr * 10)
```

Output:

```text id="wqq0pq"
[10 20 30]
```

---

# Mathematical Functions

---

# Sum

```python id="kv7gb9"
arr = np.array([1, 2, 3, 4])

print(np.sum(arr))
```

Output:

```text id="38jsmn"
10
```

---

# Mean

```python id="r7kuvl"
print(np.mean(arr))
```

Output:

```text id="8yqtmw"
2.5
```

---

# Maximum Value

```python id="7t6nmi"
print(np.max(arr))
```

Output:

```text id="u4lz8z"
4
```

---

# Minimum Value

```python id="3c2g58"
print(np.min(arr))
```

Output:

```text id="dkr4d4"
1
```

---

# Reshaping Arrays

---

# Example

```python id="nhzgm0"
arr = np.array([1, 2, 3, 4, 5, 6])

reshaped = arr.reshape(2, 3)

print(reshaped)
```

Output:

```text id="hmhwb7"
[[1 2 3]
 [4 5 6]]
```

---

# Flattening Arrays

```python id="ebj64y"
matrix = np.array([
    [1, 2],
    [3, 4]
])

flat = matrix.flatten()

print(flat)
```

Output:

```text id="f44eqo"
[1 2 3 4]
```

---

# Random Arrays

---

# Random Integers

```python id="8m9lj5"
random_numbers = np.random.randint(1, 10, size=5)

print(random_numbers)
```

---

# Random Floating Values

```python id="ynjnd7"
random_values = np.random.rand(3)

print(random_values)
```

Used in:

* AI model initialization
* simulations
* testing systems

---

# Memory Efficiency Concept

NumPy arrays use:

* fixed datatype storage
* contiguous memory allocation

Advantages:

* faster access
* lower memory usage
* optimized computation

---

# Real-World Applications

---

# AI and Machine Learning

Used for:

* tensors
* matrix operations
* neural network computation

---

# Computer Vision

Used for:

* image arrays
* pixel processing
* filtering

---

# VLSI and Hardware Engineering

Used for:

* waveform analysis
* signal processing
* timing data analysis
* simulation outputs

---

# Common Beginner Mistakes

---

# Forgetting Import

Incorrect:

```python id="zlfjlwm"
arr = array([1, 2, 3])
```

Correct:

```python id="cl7w7m"
import numpy as np

arr = np.array([1, 2, 3])
```

---

# Mixing Different Shapes

Incorrect:

```python id="lx5o1k"
a = np.array([1, 2])
b = np.array([1, 2, 3])

print(a + b)
```

This causes shape mismatch error.

---

# Best Practices

---

# Use Meaningful Variable Names

Good:

```python id="2g4vc3"
temperature_data = np.array([30, 32, 31])
```

Bad:

```python id="k8cf9h"
x = np.array([30, 32, 31])
```

---

# Prefer Vectorized Operations

Avoid unnecessary loops whenever possible.

---

# Keep Array Shapes Consistent

Always verify dimensions before operations.

---

# Interview Questions

---

# Q1. Why are NumPy arrays faster than Python lists?

### Answer

NumPy arrays:

* use contiguous memory
* use optimized C backend
* support vectorized execution

---

# Q2. What is ndarray?

### Answer

`ndarray` is the main NumPy array object.

---

# Q3. What is array slicing?

### Answer

Extracting portions of arrays using indexes.

---

# Q4. What is the difference between shape and dimension?

### Answer

| Shape          | Dimension      |
| -------------- | -------------- |
| Size structure | Number of axes |

---

# Q5. Why are arrays important in AI?

### Answer

AI models require:

* matrix operations
* tensor processing
* numerical computation

Arrays provide efficient mathematical computation.

---

# Summary

In this notebook you learned:

* NumPy arrays
* array creation
* dimensions
* shapes
* indexing
* slicing
* array operations
* reshaping
* mathematical computation

These concepts are foundational for:

* Machine Learning
* Deep Learning
* Scientific Computing
* Data Engineering
* Computer Vision
* Robotics
* VLSI Automation

Arrays are the computational backbone of modern AI systems.
