# Python Variables

Variables are used to store data in Python.

Think of a variable like a container that stores information.

---

# Creating Variables

```python
x = 10
name = "Computer"
```

---

# Printing Variables

```python
x = 10
print(x)
```

Output:

```text
10
```

---

# Multiple Variables

```python
a = 10
b = 20

print(a)
print(b)
```

---

# Variable Naming Rules

| Rule | Example |
|---|---|
| Must start with letter or `_` | `name`, `_data` |
| Cannot start with number |  `1value` |
| No spaces |  `my value` |
| Case sensitive | `age` ≠ `Age` |

---

# Valid Variable Names

```python
student_name = "John"
marks = 90
_total = 100
```

---

# Invalid Variable Names

```python
2name = "Alex"      # Invalid
my value = 10       # Invalid
```

---

# Data Types

| Type | Example |
|---|---|
| Integer | `10` |
| Float | `3.14` |
| String | `"Hello"` |
| Boolean | `True` |

---

# Checking Type

```python
x = 10

print(type(x))
```

Output:

```text
<class 'int'>
```

---

# Type Conversion

```python
x = "10"

y = int(x)

print(y)
```

---

# Input From User

```python
name = input("Enter your name: ")

print(name)
```

---

# Example Program

```python
name = "Varada"
age = 23

print("Name:", name)
print("Age:", age)
```

---

# Key Takeaways

- Variables store data
- Python automatically detects type
- Use meaningful names
- Variables are essential in programming
