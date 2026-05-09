# Object Oriented Programming (OOP) in Python

OOP organizes code using objects and classes.

Used heavily in:
- AI systems
- Software engineering
- Game development
- Web applications

---

# Real-Life Analogy

Think of:

| Real World | Programming |
|---|---|
| Car blueprint | Class |
| Actual car | Object |

---

# What is a Class?

A class is a blueprint for creating objects.

---

# Creating a Class

```python
class Student:

    pass
```

---

# Creating Object

```python
s1 = Student()
```

---

# Constructor (`__init__`)

Used to initialize object data.

```python
class Student:

    def __init__(self, name, age):

        self.name = name
        self.age = age
```

---

# Creating Object

```python
s1 = Student("Varada", 23)

print(s1.name)
print(s1.age)
```

---

# Methods

Functions inside class.

```python
class Student:

    def greet(self):

        print("Hello")
```

---

# Example

```python
class Student:

    def __init__(self, name):

        self.name = name

    def show(self):

        print(self.name)

s1 = Student("Varada")

s1.show()
```

---

# self Keyword

`self` refers to current object.

---

# Multiple Objects

```python
s1 = Student("A")
s2 = Student("B")
```

---

# Inheritance

One class inherits another.

---

# Example

```python
class Animal:

    def sound(self):

        print("Animal sound")

class Dog(Animal):

    def bark(self):

        print("Dog barking")

d = Dog()

d.sound()
d.bark()
```

---

# Encapsulation

Hide internal data.

```python
class Bank:

    def __init__(self):

        self.__balance = 1000
```

---

# Polymorphism

Same function behaves differently.

---

# Example

```python
class Cat:

    def sound(self):

        print("Meow")

class Dog:

    def sound(self):

        print("Bark")
```

---

# Why OOP Matters in AI?

OOP is used in:
- TensorFlow
- PyTorch
- AI frameworks
- APIs
- System design

---

# Key Takeaways

- Class → blueprint
- Object → real instance
- OOP organizes large systems
- Inheritance improves reusability
- OOP is heavily used in modern AI frameworks
