# Matrix Operations using NumPy

## Overview

Matrix operations are one of the most important concepts in:

* Artificial Intelligence
* Machine Learning
* Deep Learning
* Computer Vision
* Robotics
* Signal Processing
* Scientific Computing
* VLSI Modeling
* Hardware Acceleration

Modern AI systems internally perform massive matrix computations.

Examples:

* Neural Networks
* Transformers
* GPUs
* Tensor Computation
* Recommendation Systems

NumPy provides optimized tools for fast matrix operations.

---

# Learning Goals

By the end of this notebook, you will understand:

* What matrices are
* How to create matrices
* Matrix addition
* Matrix subtraction
* Matrix multiplication
* Element-wise operations
* Transpose
* Determinant
* Inverse
* Dot product
* Matrix dimensions
* Real-world AI applications

---

# 1. What is a Matrix?

A matrix is a rectangular arrangement of numbers in rows and columns.

Example:

```text id="u5vh3w"
[1  2  3]
[4  5  6]
```

This matrix contains:

* 2 rows
* 3 columns

---

# 2. Import NumPy

```python id="0exuk4"
import numpy as np
```

---

# 3. Creating Matrices

---

## Basic Matrix Creation

```python id="0xtljr"
A = np.array([
    [1, 2],
    [3, 4]
])

print(A)
```

Output:

```text id="mjlwmr"
[[1 2]
 [3 4]]
```

---

## Matrix Dimensions

```python id="x6p5py"
print(A.shape)
```

Output:

```text id="u9f6n0"
(2, 2)
```

Meaning:

* 2 rows
* 2 columns

---

# 4. Matrix Addition

---

## Concept

Two matrices can be added if they have the same dimensions.

---

## Example

```python id="5s9ydo"
A = np.array([
    [1, 2],
    [3, 4]
])

B = np.array([
    [5, 6],
    [7, 8]
])

C = A + B

print(C)
```

Output:

```text id="mjlwmr"
[[ 6  8]
 [10 12]]
```

---

## Real-World Use

Matrix addition is used in:

* image processing
* neural networks
* signal summation
* feature combination

---

# 5. Matrix Subtraction

---

## Example

```python id="clwwyv"
A = np.array([
    [10, 20],
    [30, 40]
])

B = np.array([
    [1, 2],
    [3, 4]
])

print(A - B)
```

Output:

```text id="u9s5dc"
[[ 9 18]
 [27 36]]
```

---

# 6. Element-wise Multiplication

---

## Concept

Each element is multiplied individually.

---

## Example

```python id="fe2v3y"
A = np.array([
    [1, 2],
    [3, 4]
])

B = np.array([
    [5, 6],
    [7, 8]
])

print(A * B)
```

Output:

```text id="qjlwmr"
[[ 5 12]
 [21 32]]
```

---

# 7. Matrix Multiplication

---

## Important Concept

Matrix multiplication is different from element-wise multiplication.

This operation is heavily used in:

* AI
* Deep Learning
* Graphics
* Robotics
* Hardware accelerators

---

## Mathematical Representation

```text id="jlwmr1"
A × B
```

---

## Example

```python id="v3axt8"
A = np.array([
    [1, 2],
    [3, 4]
])

B = np.array([
    [5, 6],
    [7, 8]
])

print(np.dot(A, B))
```

OR

```python id="r7fwy1"
print(A @ B)
```

Output:

```text id="q0qdxm"
[[19 22]
 [43 50]]
```

---

# 8. Understanding Matrix Multiplication

---

## Internal Computation

```text id="s90ykv"
[1 2]   [5 6]
[3 4] × [7 8]
```

Calculation:

```text id="vzjlwm"
(1×5 + 2×7) = 19
(1×6 + 2×8) = 22
```

---

# 9. Matrix Transpose

---

## What is Transpose?

Transpose converts:

* rows into columns
* columns into rows

---

## Example

```python id="6jlwm9"
A = np.array([
    [1, 2, 3],
    [4, 5, 6]
])

print(A.T)
```

Output:

```text id="l2fby2"
[[1 4]
 [2 5]
 [3 6]]
```

---

## Applications

Transpose is used in:

* neural networks
* linear algebra
* covariance computation
* signal transformation

---

# 10. Identity Matrix

---

## Concept

An identity matrix has:

* 1s on diagonal
* 0s elsewhere

---

## Example

```python id="jjlwm1"
I = np.eye(3)

print(I)
```

Output:

```text id="jlwmr4"
[[1. 0. 0.]
 [0. 1. 0.]
 [0. 0. 1.]]
```

---

# 11. Matrix Determinant

---

## What is Determinant?

A determinant helps determine:

* matrix invertibility
* linear dependence
* geometric scaling

---

## Example

```python id="rjlwm2"
A = np.array([
    [1, 2],
    [3, 4]
])

print(np.linalg.det(A))
```

Output:

```text id="jlwmr5"
-2.0
```

---

# 12. Matrix Inverse

---

## Concept

The inverse matrix reverses matrix transformation.

---

## Example

```python id="djlwm3"
A = np.array([
    [1, 2],
    [3, 4]
])

inverse = np.linalg.inv(A)

print(inverse)
```

---

## Applications

Used in:

* solving equations
* ML optimization
* control systems
* graphics
* robotics

---

# 13. Dot Product

---

## Concept

Dot product combines:

* multiplication
* summation

---

## Example

```python id="xjlwm4"
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

print(np.dot(a, b))
```

Output:

```text id="jlwmr6"
32
```

Calculation:

```text id="jlwmr7"
1×4 + 2×5 + 3×6
= 4 + 10 + 18
= 32
```

---

# 14. Random Matrices

---

## Creating Random Matrix

```python id="zjlwm5"
random_matrix = np.random.rand(3, 3)

print(random_matrix)
```

---

## Applications

Used in:

* AI model initialization
* simulations
* stochastic systems
* testing

---

# 15. Matrix Reshaping

---

## Example

```python id="cjlwm6"
arr = np.array([1, 2, 3, 4, 5, 6])

reshaped = arr.reshape(2, 3)

print(reshaped)
```

Output:

```text id="jlwmr8"
[[1 2 3]
 [4 5 6]]
```

---

# 16. Matrix Flattening

---

## Example

```python id="vjlwm7"
matrix = np.array([
    [1, 2],
    [3, 4]
])

print(matrix.flatten())
```

Output:

```text id="jlwmr9"
[1 2 3 4]
```

---

# 17. Broadcasting with Matrices

---

## Example

```python id="njlwm8"
matrix = np.array([
    [1, 2],
    [3, 4]
])

print(matrix + 10)
```

Output:

```text id="jlwmr0"
[[11 12]
 [13 14]]
```

---

# 18. Matrix Operations in AI

---

## Neural Networks

AI models perform:

```text id="mjlwm1"
Input × Weights + Bias
```

This is matrix multiplication.

---

## Deep Learning

Used in:

* CNNs
* Transformers
* Attention Mechanisms
* Tensor Computation

---

# 19. Matrix Operations in VLSI

---

## Applications

Used in:

* DSP systems
* image accelerators
* AI hardware
* systolic arrays
* tensor accelerators
* FPGA-based AI engines

---

## Hardware Acceleration

Modern AI chips optimize:

* matrix multiplication
* tensor operations
* vector computation

Examples:

* GPUs
* TPUs
* AI accelerators

---

# 20. Common Beginner Mistakes

---

## Confusing * with Matrix Multiplication

Incorrect assumption:

```python id="8jlwm2"
A * B
```

This performs element-wise multiplication.

Correct matrix multiplication:

```python id="pjlwm3"
A @ B
```

OR

```python id="qjlwm4"
np.dot(A, B)
```

---

## Shape Mismatch Error

Incorrect:

```python id="wjlwm5"
A = np.array([[1, 2]])
B = np.array([[1, 2]])

print(A @ B)
```

Dimensions are incompatible.

---

# 21. Performance Advantage of NumPy

---

## Why NumPy is Fast

NumPy uses:

* optimized C backend
* vectorized execution
* contiguous memory layout

This makes matrix operations extremely efficient.

---

# 22. Interview Questions

---

## Q1. Difference between element-wise multiplication and matrix multiplication?

### Answer

| Element-wise                      | Matrix Multiplication              |
| --------------------------------- | ---------------------------------- |
| Uses `*`                          | Uses `@` or `dot()`                |
| Multiplies corresponding elements | Performs row-column multiplication |

---

## Q2. What is transpose?

### Answer

Transpose converts rows into columns.

---

## Q3. What is determinant?

### Answer

A value representing matrix properties like invertibility.

---

## Q4. Why are matrices important in AI?

### Answer

AI models internally use matrix operations for:

* neural computation
* tensor processing
* feature transformation

---

## Q5. What is vectorization?

### Answer

Performing operations on entire arrays without explicit Python loops.

---

# 23. Summary

In this notebook you learned:

* Matrix creation
* Matrix addition
* Matrix subtraction
* Matrix multiplication
* Dot product
* Transpose
* Determinant
* Inverse
* Broadcasting
* Reshaping
* Vectorized computation

These concepts are foundational for:

* Artificial Intelligence
* Machine Learning
* Deep Learning
* Robotics
* Scientific Computing
* Hardware Acceleration
* GPU Computing
* AI Chip Design
* DSP Systems
* FPGA AI Architectures

---

# Next Learning Path

Continue with:

```text id="yjlwm6"
broadcasting.ipynb
vectorization.ipynb
linear_algebra/
machine_learning/
deep_learning_basics/
```

Matrix operations form the computational backbone of modern AI systems.
