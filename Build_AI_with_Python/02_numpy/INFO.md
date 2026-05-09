# NumPy Foundations

## Overview

NumPy (Numerical Python) is one of the most important Python libraries for:

* Scientific Computing
* Machine Learning
* AI Development
* Data Analysis
* Signal Processing
* Computer Vision
* Hardware Acceleration Research
* Matrix Computation

NumPy provides:

* Fast array operations
* Mathematical computation tools
* Matrix processing
* Linear algebra support
* High-performance numerical execution

It is the foundation of:

* Pandas
* TensorFlow
* PyTorch
* Scikit-learn
* OpenCV
* Deep Learning frameworks

---

# Why NumPy is Important

Without NumPy:

* Python numerical operations become slow
* Large-scale data processing becomes difficult
* AI computation becomes inefficient

NumPy solves this using:

* Optimized C-based execution
* Vectorized computation
* Efficient memory management

---

# Learning Goals

By the end of this module, you will understand:

* What NumPy is
* Why arrays are faster than lists
* How to create arrays
* Mathematical operations on arrays
* Matrix computation basics
* Broadcasting
* Vectorization
* Performance optimization concepts

---

# Folder Structure

```text
02_numpy/
│
├── README.md
├── arrays.ipynb
├── matrix_operations.ipynb
├── broadcasting.ipynb
└── vectorization.ipynb
```

---

# Installing NumPy

Install NumPy using pip:

```python id="pcwwkz"
pip install numpy
```

Import NumPy:

```python id="0svfc4"
import numpy as np
```

`np` is the standard alias used worldwide.

---

# 1. NumPy Arrays

---

## What is an Array?

An array is a collection of elements stored in continuous memory locations.

Arrays are:

* faster
* memory efficient
* optimized for numerical operations

---

## Creating Arrays

### Example 1: Basic Array

```python id="jxv42u"
import numpy as np

arr = np.array([1, 2, 3, 4])

print(arr)
```

Output:

```text
[1 2 3 4]
```

---

## Difference Between List and Array

### Python List

```python id="0wj8fg"
numbers = [1, 2, 3, 4]
```

### NumPy Array

```python id="r8tvow"
numbers = np.array([1, 2, 3, 4])
```

---

## Why NumPy Arrays are Faster

NumPy arrays:

* use contiguous memory
* use optimized C backend
* avoid Python loop overhead

This makes them ideal for:

* AI workloads
* matrix multiplication
* large datasets
* scientific computation

---

# 2. Array Properties

---

## Checking Shape

```python id="drj9vj"
arr = np.array([[1, 2], [3, 4]])

print(arr.shape)
```

Output:

```text
(2, 2)
```

Meaning:

* 2 rows
* 2 columns

---

## Checking Dimensions

```python id="c4o4pc"
print(arr.ndim)
```

Output:

```text
2
```

---

## Checking Data Type

```python id="tw52vs"
print(arr.dtype)
```

Output:

```text
int64
```

---

# 3. Creating Special Arrays

---

## Array of Zeros

```python id="sy8lcn"
zeros = np.zeros((2, 3))

print(zeros)
```

Output:

```text
[[0. 0. 0.]
 [0. 0. 0.]]
```

---

## Array of Ones

```python id="yt2n4y"
ones = np.ones((3, 3))

print(ones)
```

---

## Identity Matrix

```python id="7o8a4n"
identity = np.eye(3)

print(identity)
```

Output:

```text
[[1. 0. 0.]
 [0. 1. 0.]
 [0. 0. 1.]]
```

Used heavily in:

* linear algebra
* AI models
* transformation systems

---

# 4. Array Indexing

---

## Accessing Elements

```python id="x7q4sx"
arr = np.array([10, 20, 30])

print(arr[1])
```

Output:

```text
20
```

---

## 2D Array Access

```python id="ruwjlwm"
matrix = np.array([
    [1, 2],
    [3, 4]
])

print(matrix[1][0])
```

Output:

```text
3
```

---

# 5. Array Slicing

---

## Basic Slicing

```python id="t4ce2n"
arr = np.array([1, 2, 3, 4, 5])

print(arr[1:4])
```

Output:

```text
[2 3 4]
```

---

## Step Slicing

```python id="lb0o3u"
print(arr[::2])
```

Output:

```text
[1 3 5]
```

---

# 6. Mathematical Operations

---

## Addition

```python id="7s2n4u"
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

print(a + b)
```

Output:

```text
[5 7 9]
```

---

## Multiplication

```python id="c1hy3t"
print(a * b)
```

Output:

```text
[ 4 10 18]
```

---

## Scalar Operations

```python id="wk4n6p"
print(a * 10)
```

Output:

```text
[10 20 30]
```

---

# 7. Matrix Operations

---

## Matrix Addition

```python id="b4m60l"
A = np.array([
    [1, 2],
    [3, 4]
])

B = np.array([
    [5, 6],
    [7, 8]
])

print(A + B)
```

---

## Matrix Multiplication

```python id="4r6zwd"
print(np.dot(A, B))
```

OR

```python id="wo93xw"
print(A @ B)
```

---

# 8. Broadcasting

---

## What is Broadcasting?

Broadcasting allows NumPy to perform operations on arrays of different sizes.

---

## Example

```python id="g1v52z"
arr = np.array([1, 2, 3])

print(arr + 10)
```

Output:

```text
[11 12 13]
```

The scalar `10` is automatically expanded.

---

## Why Broadcasting is Powerful

Used in:

* image processing
* neural networks
* tensor operations
* feature scaling
* signal computation

---

# 9. Vectorization

---

## What is Vectorization?

Vectorization means:
performing operations on entire arrays without explicit Python loops.

---

## Traditional Loop

```python id="nt6slh"
numbers = [1, 2, 3, 4]

result = []

for i in numbers:
    result.append(i * 2)

print(result)
```

---

## Vectorized NumPy Operation

```python id="vcy4h0"
arr = np.array([1, 2, 3, 4])

print(arr * 2)
```

---

## Why Vectorization Matters

Advantages:

* faster execution
* cleaner code
* optimized computation
* better scalability

Very important in:

* AI
* ML
* scientific computing
* simulations

---

# 10. Random Number Generation

---

## Random Integers

```python id="l41dzf"
random_numbers = np.random.randint(1, 10, size=5)

print(random_numbers)
```

---

## Random Floats

```python id="p61krd"
random_values = np.random.rand(3)

print(random_values)
```

Used in:

* AI model initialization
* simulations
* testing
* stochastic systems

---

# 11. Useful NumPy Functions

---

## Mean

```python id="w85d8i"
arr = np.array([1, 2, 3, 4])

print(np.mean(arr))
```

---

## Sum

```python id="afp7wy"
print(np.sum(arr))
```

---

## Maximum

```python id="z1xgzb"
print(np.max(arr))
```

---

## Minimum

```python id="q6sx8w"
print(np.min(arr))
```

---

# 12. Real-World Applications of NumPy

---

## AI and Machine Learning

Used for:

* tensor operations
* neural networks
* feature engineering
* preprocessing

---

## Data Science

Used for:

* numerical analysis
* matrix computation
* statistical operations

---

## Signal Processing

Used for:

* FFT
* waveform analysis
* filtering

---

## VLSI and Hardware Automation

Used for:

* simulation data analysis
* waveform processing
* timing report analysis
* numerical computation
* hardware acceleration research

---

# 13. Performance Advantage Example

---

## Python List Computation

```python id="5nqjnd"
numbers = [1, 2, 3, 4]

result = []

for i in numbers:
    result.append(i * 2)
```

---

## NumPy Computation

```python id="6t3ymk"
arr = np.array([1, 2, 3, 4])

result = arr * 2
```

NumPy internally uses optimized low-level computation, making it significantly faster.

---

# 14. Common Beginner Mistakes

---

## Forgetting np Alias

Incorrect:

```python id="vwb48e"
array([1, 2, 3])
```

Correct:

```python id="v72x0o"
np.array([1, 2, 3])
```

---

## Mixing Array Shapes

Incorrect:

```python id="gvy3tf"
a = np.array([1, 2])
b = np.array([1, 2, 3])

print(a + b)
```

This causes shape mismatch error.

---

# 15. Best Practices

---

## Use Vectorized Operations

Avoid unnecessary loops.

---

## Keep Arrays Consistent

Maintain proper shapes and dimensions.

---

## Use Meaningful Variable Names

Good:

```python id="wy3xzw"
temperature_data = np.array([30, 32, 31])
```

Bad:

```python id="4t7icq"
x = np.array([30, 32, 31])
```

---

# 16. Interview Questions

---

## Q1. Why is NumPy faster than Python lists?

### Answer

NumPy uses:

* contiguous memory
* vectorized execution
* optimized C backend

---

## Q2. What is broadcasting?

### Answer

Broadcasting allows arithmetic operations between arrays of different shapes.

---

## Q3. What is vectorization?

### Answer

Performing array operations without explicit loops.

---

## Q4. Difference between list and NumPy array?

### Answer

| Python List    | NumPy Array    |
| -------------- | -------------- |
| Slower         | Faster         |
| Flexible types | Fixed datatype |
| More memory    | Less memory    |

---

## Q5. What is ndarray?

### Answer

The core NumPy array object.

---

# Summary

In this module you learned:

* NumPy basics
* Arrays
* Matrix operations
* Broadcasting
* Vectorization
* Numerical computation
* Performance optimization

These concepts are foundational for:

* Machine Learning
* Deep Learning
* AI Systems
* Robotics
* Computer Vision
* Scientific Computing
* VLSI Automation
* Hardware Acceleration Research

---

# Next Learning Path

After NumPy, continue with:

```text
03_pandas/
04_data_visualization/
05_statistics/
06_linear_algebra/
07_machine_learning/
```

NumPy is the mathematical engine powering modern AI systems.
