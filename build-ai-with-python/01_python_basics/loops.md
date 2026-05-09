# Python Loops

Loops are used to repeat tasks.

Instead of writing the same code multiple times, loops automate repetition.

---

# Types of Loops

| Loop | Purpose |
|---|---|
| for loop | Repeat fixed number of times |
| while loop | Repeat until condition becomes false |

---

# for Loop

```python
for i in range(5):
    print(i)
```

Output:

```text
0
1
2
3
4
```

---

# Understanding `range()`

| Syntax | Meaning |
|---|---|
| `range(5)` | 0 → 4 |
| `range(1,5)` | 1 → 4 |
| `range(1,10,2)` | step size 2 |

---

# Example

```python
for i in range(1,6):
    print(i)
```

Output:

```text
1
2
3
4
5
```

---

# Loop Through List

```python
names = ["Alice", "Bob", "Charlie"]

for name in names:
    print(name)
```

---

# while Loop

```python
count = 0

while count < 5:
    print(count)
    count += 1
```

---

# Infinite Loop

```python
while True:
    print("Running forever")
```

⚠ Avoid infinite loops unless required.

---

# break Statement

Used to stop loop.

```python
for i in range(10):

    if i == 5:
        break

    print(i)
```

---

# continue Statement

Skip current iteration.

```python
for i in range(5):

    if i == 2:
        continue

    print(i)
```

---

# Nested Loops

```python
for i in range(3):

    for j in range(2):

        print(i, j)
```

---

# Real-Life Example

ATM checking multiple users:

```python
users = ["A", "B", "C"]

for user in users:
    print("Checking account:", user)
```

---

# Key Takeaways

- Loops automate repetition
- `for` loop → fixed iterations
- `while` loop → condition based
- `break` stops loop
- `continue` skips iteration
