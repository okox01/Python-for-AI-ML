
---

# Python Mastery Notes

# Chapter 3 — Data Types (Complete Guide)

---

# What is a Data Type?

## Real-Life Analogy

Imagine you have different containers:

🥤 Water Bottle → Stores water

📦 Box → Stores books

💰 Wallet → Stores money

📱 Phone → Stores apps

Each container is designed to hold a certain kind of thing.

Python works the same way.

Different types of data are represented by different data types.

Example:

```python
age = 21
```

Here:

* Variable → `age`
* Value → `21`
* Data Type → `int`

---

# Why Do We Need Data Types?

Suppose Python didn't know the type.

```python
10 + 20
```

Should it:

* Add?
* Join?
* Multiply?
* Compare?

Python needs to know the type of data to decide what operations are valid.

---

# Python Built-in Data Types

Python has many built-in types, but the most important ones are:

| Category | Data Types                         |
| -------- | ---------------------------------- |
| Numeric  | `int`, `float`, `complex`          |
| Boolean  | `bool`                             |
| Text     | `str`                              |
| Sequence | `list`, `tuple`, `range`           |
| Mapping  | `dict`                             |
| Set      | `set`, `frozenset`                 |
| Binary   | `bytes`, `bytearray`, `memoryview` |
| Special  | `NoneType`                         |

We'll master each one.

---

# Numeric Types

## 1. Integer (`int`)

Integers are whole numbers.

Examples:

```python
10

0

-50

99999999999
```

Python code:

```python
age = 21

population = 180000000

temperature = -5

print(type(age))
```

Output:

```python
<class 'int'>
```

---

## Where Are Integers Used?

AI:

```python
epochs = 100
```

Data Science:

```python
number_of_rows = 5000
```

Game Development:

```python
player_score = 1500
```

Web:

```python
user_id = 105
```

---

# Python Integers Have No Fixed Limit

Unlike some languages, Python integers can grow very large.

```python
num = 999999999999999999999999999999999999999999

print(num)
```

Python handles this automatically (limited mainly by available memory).

---

# Arithmetic Operations

```python
a = 20
b = 3

print(a + b)
print(a - b)
print(a * b)
print(a / b)
print(a // b)
print(a % b)
print(a ** b)
```

Output:

```text
23
17
60
6.666666666666667
6
2
8000
```

Explanation:

`/` → True division

`//` → Floor division

`%` → Remainder

`**` → Power

---

# Real-Life Example

Suppose:

You have 20 chocolates.

You give each friend 3 chocolates.

```python
20 // 3
```

Means:

How many complete friends can receive chocolates?

Answer:

```text
6
```

Remaining:

```python
20 % 3
```

Answer:

```text
2
```

---

# Floor Division (`//`)

Many beginners think:

```python
5 // 2
```

equals

```text
2.5
```

Wrong.

Output:

```text
2
```

It removes the fractional part by rounding down toward negative infinity.

More examples:

```python
print(10 // 4)
print(7 // 3)
print(100 // 9)
```

Outputs:

```text
2
2
11
```

---

# Negative Floor Division

This surprises many people.

```python
print(-5 // 2)
```

Output:

```text
-3
```

Why?

Because Python rounds **down**, not toward zero.

Number line:

```text
-3      -2

------|------|

    -2.5
```

The next lower integer is `-3`.

---

# Modulus (`%`)

Returns the remainder.

```python
10 % 3
```

Output:

```text
1
```

Examples:

```python
15 % 5
```

Output:

```text
0
```

```python
20 % 7
```

Output:

```text
6
```

---

# Real AI Example

Suppose your dataset contains 103 samples.

Batch size:

```python
32
```

How many full batches?

```python
103 // 32
```

Output:

```text
3
```

Remaining samples?

```python
103 % 32
```

Output:

```text
7
```

---

# Exponent (`**`)

```python
2 ** 3
```

Output:

```text
8
```

Because:

```text
2 × 2 × 2
```

---

# Float (`float`)

Floats represent numbers with decimal points.

Examples:

```python
3.14

-0.75

100.5

0.0
```

Python code:

```python
pi = 3.14159

height = 5.6

print(type(pi))
```

Output:

```python
<class 'float'>
```

---

# Where Are Floats Used?

Machine Learning:

```python
learning_rate = 0.001
```

Probability:

```python
0.87
```

Statistics:

```python
mean = 25.6
```

Physics:

```python
velocity = 9.81
```

---

# Floating-Point Precision

One of Python's most famous examples:

```python
print(0.1 + 0.2)
```

Output:

```text
0.30000000000000004
```

Not:

```text
0.3
```

Why?

Computers store floating-point numbers in binary, and many decimal fractions cannot be represented exactly. This tiny rounding error is normal in most programming languages.

Instead of comparing floats directly:

```python
a = 0.1 + 0.2
print(a == 0.3)
```

Prefer checking whether the difference is very small:

```python
tolerance = 1e-9
print(abs(a - 0.3) < tolerance)
```

We'll also learn the `math.isclose()` function later.

---

# Complex Numbers (`complex`)

Python supports complex numbers directly.

Example:

```python
z = 3 + 4j

print(type(z))
```

Output:

```python
<class 'complex'>
```

Access parts:

```python
print(z.real)
print(z.imag)
```

Output:

```text
3.0
4.0
```

Complex numbers are used in fields such as signal processing and some areas of scientific computing.

---

# Boolean (`bool`)

A Boolean has only two possible values:

```python
True

False
```

Examples:

```python
is_logged_in = True

is_admin = False
```

Type:

```python
print(type(True))
```

Output:

```python
<class 'bool'>
```

---

# Boolean Arithmetic

In Python:

```python
True == 1

False == 0
```

Example:

```python
print(True + True)
print(True + False)
```

Output:

```text
2
1
```

This works because `bool` is a subclass of `int` in Python.

---

# `None`

`None` means:

> "No value" or "nothing assigned."

Example:

```python
result = None

print(result)
```

Output:

```text
None
```

Useful when you don't yet have a value:

```python
best_model = None
```

Later:

```python
best_model = trained_model
```

---

# Checking Types

```python
x = 10

print(type(x))
```

Better when checking a specific type:

```python
print(isinstance(x, int))
```

Output:

```text
True
```

`isinstance()` also works correctly with inheritance, so it's usually preferred over comparing `type(...)` directly.

---

# Type Conversion

Convert an integer to a float:

```python
x = 10

print(float(x))
```

Output:

```text
10.0
```

Convert a float to an integer:

```python
print(int(5.99))
```

Output:

```text
5
```

Notice that `int()` truncates toward zero; it does **not** round.

Convert a string to an integer:

```python
age = "21"

print(int(age))
```

Output:

```text
21
```

Convert an integer to a string:

```python
number = 50

print(str(number))
```

Output:

```text
"50"
```

---

# Common Mistakes

### Mistake 1

```python
age = "21"

print(age + 5)
```

❌ Error: you can't add a string and an integer.

Correct:

```python
print(int(age) + 5)
```

---

### Mistake 2

```python
print(int("3.5"))
```

❌ Error.

Correct:

```python
print(int(float("3.5")))
```

Output:

```text
3
```

---

### Mistake 3

```python
print(bool(""))
```

Output:

```text
False
```

Many beginners expect `True`.

An empty string is considered "falsy."

---

# Truthy and Falsy Values

In conditions, Python treats some values as `False` automatically.

Falsy values include:

```python
False
None
0
0.0
''
[]
{}
set()
```

Everything else is generally truthy.

Example:

```python
if []:
    print("Runs")
else:
    print("Empty list is falsy")
```

Output:

```text
Empty list is falsy
```

---

# Practice

Predict the outputs without running the code:

```python
print(type(100))
```

```python
print(type(100.0))
```

```python
print(type(3 + 5j))
```

```python
print(bool(0))
```

```python
print(bool("Python"))
```

```python
print(int(8.99))
```

```python
print(float("25"))
```

```python
print(7 // 2)
```

```python
print(-7 // 2)
```

```python
print(7 % 2)
```

---

# Mini Project

Store information about a machine learning experiment:

```python
experiment_name = "Spam Detection"

epochs = 50

learning_rate = 0.001

accuracy = 98.75

model_trained = True

best_model = None

print("Experiment:", experiment_name)
print("Epochs:", epochs)
print("Learning Rate:", learning_rate)
print("Accuracy:", accuracy)
print("Trained:", model_trained)
print("Best Model:", best_model)
```

---

# Chapter Summary

| Data Type  | Example | Mutable? | Common Use                      |
| ---------- | ------- | -------- | ------------------------------- |
| `int`      | `42`    | No       | Counts, IDs, epochs             |
| `float`    | `3.14`  | No       | Measurements, learning rates    |
| `complex`  | `2+3j`  | No       | Scientific computing            |
| `bool`     | `True`  | No       | Decisions and conditions        |
| `NoneType` | `None`  | No       | Missing or uninitialized values |

## Key Takeaways

* Every value in Python has a data type.
* Numeric types include `int`, `float`, and `complex`.
* `bool` has only `True` and `False`.
* `None` represents the absence of a value.
* Use `type()` to inspect a type and `isinstance()` to test for one.
* Be careful with floating-point precision.
* Learn type conversion because user input is often received as strings.

---

