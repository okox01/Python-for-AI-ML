# Variables

## How we'll learn

Each lesson will have this structure:

1. **Theory (What & Why)**
2. **Real-life analogy**
3. **Syntax**
4. **Every possible scenario**
5. **Common mistakes**
6. **Professional usage**
7. **Interview questions**
8. **AI/ML applications**
9. **Practice problems**
10. **Mini project**
11. **Summary notes**

We'll make these notes so complete that you can revise them months later.

---

# Python Mastery Notes

# Chapter 1 — Variables

---

# What is a Variable?

Imagine you have several boxes.

Each box has:

* a label (name)
* something stored inside

```
┌────────────┐
│ age        │
│    21      │
└────────────┘
```

Here,

```
age
```

is the variable.

```
21
```

is the value.

A variable is simply **a name that refers to an object in memory**.

---

# Real Definition

A variable is a reference (or binding) to an object stored in memory.

Python variables do **not** directly hold values. They point to objects.

Example

```python
age = 21
```

Many beginners think:

```
age
 ↓
21
```

Internally Python does something closer to:

```
age
 │
 ▼
+------+
|  21  |
+------+
```

The object `21` exists in memory, and `age` refers to it.

---

# Why do Variables Exist?

Without variables:

```python
print(5000)

print(5000)

print(5000)
```

What if salary changes?

You would have to change every occurrence.

Instead:

```python
salary = 5000

print(salary)
print(salary)
print(salary)
```

Now you update it only once.

---

# Creating Variables

```python
name = "Sami"

age = 21

height = 5.5

student = True
```

Python automatically determines the type of object on the right-hand side.

---

# Variable Naming Rules

Allowed:

```python
student_name = "Sami"

student1 = "Ali"

_student = "John"

student_name_1 = "Alex"
```

Not allowed:

```python
1student = "Sami"      # starts with number

student-name = "Sami"  # hyphen

class = 5              # keyword
```

---

# Naming Convention

Use **snake_case** in Python.

Good:

```python
student_name

total_marks

average_salary
```

Bad:

```python
StudentName

Student_name

studentName
```

---

# Multiple Assignment

Instead of

```python
x = 5

y = 10

z = 15
```

You can write

```python
x, y, z = 5, 10, 15
```

---

# Assign Same Value

```python
x = y = z = 100
```

All variables refer to the same integer object (`100`).

---

# Swapping Variables

Traditional way:

```python
temp = a

a = b

b = temp
```

Pythonic way:

```python
a, b = b, a
```

Example

```python
a = 10
b = 20

a, b = b, a

print(a)
print(b)
```

Output

```
20
10
```

---

# Dynamic Typing

In languages like C:

```c
int age = 20;
```

In Python:

```python
age = 20

age = "Twenty"
```

Python allows rebinding the name to a different type.

---

# Checking Type

```python
age = 20

print(type(age))
```

Output

```python
<class 'int'>
```

More examples

```python
print(type(3.5))

print(type(True))

print(type("Python"))
```

---

# Object Identity

Python provides `id()` to inspect an object's identity.

```python
x = 10

print(id(x))
```

The exact number varies each run.

---

# Copying Variables

```python
a = 10

b = a
```

Diagram

```
a ───┐
     │
     ▼
   +----+
   | 10 |
   +----+
     ▲
     │
b ───┘
```

Both names refer to the same integer object.

---

# Updating

```python
a = 10

b = a

a = 20
```

Now:

```
a → 20

b → 10
```

`a` is rebound to a different object; `b` still refers to the original integer.

---

# Deleting Variable

```python
x = 100

del x
```

Now

```python
print(x)
```

Produces

```
NameError
```

---

# Reserved Keywords

These cannot be variable names.

Examples

```python
if

for

while

class

def

return

True

False

None
```

---

# Good Naming

Bad

```python
a = 20

b = 300
```

Good

```python
student_age = 20

employee_salary = 300
```

Your future self (or teammates) will thank you.

---

# AI/ML Example

Instead of

```python
x = 0.01

y = 500

z = 32
```

Write

```python
learning_rate = 0.01

epochs = 500

batch_size = 32
```

This is much easier to understand and maintain.

---

# Common Beginner Mistakes

### Mistake 1

```python
student-name = "Sami"
```

❌ `-` is treated as subtraction.

Correct:

```python
student_name = "Sami"
```

---

### Mistake 2

```python
print(Name)
```

after defining

```python
name = "Sami"
```

Python is case-sensitive.

`Name` and `name` are different identifiers.

---

### Mistake 3

```python
print(age)

age = 20
```

Variables must be assigned before use.

---

# Practice

Predict the output:

```python
a = 5
b = a
a = 100

print(a)
print(b)
```

---

```python
x = y = 10

y = 20

print(x)
print(y)
```

---

```python
name = "Sami"

print(type(name))
```

---

# Mini Project

Create a student profile.

```python
student_name = "Sami"
student_id = 221345
department = "CSE"
cgpa = 3.85
is_graduated = False

print("Student Information")
print("-------------------")
print(student_name)
print(student_id)
print(department)
print(cgpa)
print(is_graduated)
```

---

# Chapter Summary

* A variable is a **name bound to an object**.
* Python is **dynamically typed**.
* Use **meaningful names** (`learning_rate` instead of `x`).
* Variables can be rebound to different objects.
* Use `type()` to inspect an object's type.
* Use `id()` to inspect an object's identity.
* Follow **snake_case** naming.
* Prefer multiple assignment and tuple unpacking where appropriate.

---
