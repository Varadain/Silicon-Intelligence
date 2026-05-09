# Python Functions

Functions are reusable blocks of code.

Instead of writing the same code repeatedly, functions allow reuse.

---

# Why Functions?

| Benefit | Description |
|---|---|
| Reusability | Write once, use many times |
| Cleaner code | Organized structure |
| Easier debugging | Isolated logic |

---

# Creating a Function

```python
def greet():
    print("Hello")
```

---

# Calling Function

```python
greet()
```

Output:

```text
Hello
```

---

# Function With Parameters

```python
def greet(name):

    print("Hello", name)
```

---

# Calling Function

```python
greet("Varada")
```

Output:

```text
Hello Varada
```

---

# Return Statement

Functions can return values.

```python
def add(a, b):

    return a + b
```

---

# Example

```python
result = add(10, 20)

print(result)
```

Output:

```text
30
```

---

# Default Parameters

```python
def greet(name="Guest"):

    print(name)
```

---

# Keyword Arguments

```python
def student(name, age):

    print(name, age)

student(age=23, name="Varada")
```

---

# Variable Scope

| Scope | Meaning |
|---|---|
| Local | Inside function |
| Global | Outside function |

---

# Example

```python
x = 10

def show():

    x = 20

    print(x)

show()

print(x)
```

Output:

```text
20
10
```

---

# Lambda Function

Small anonymous function.

```python
square = lambda x: x*x

print(square(5))
```

---

# Real-Life Example

Calculator:

```python
def multiply(a, b):

    return a * b

print(multiply(5, 6))
```

---

# Key Takeaways

- Functions improve reusability
- Parameters pass data
- `return` gives output
- Functions simplify large programs
