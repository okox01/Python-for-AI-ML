Excellent. Now we start one of the **most important topics in Python**. This single chapter will explain **why Python behaves the way it does**.

> **Many Python programmers skip this chapter. Professional Python developers understand it deeply.**

Once you understand this, topics like Lists, Dictionaries, Functions, Classes, NumPy, Pandas, and even PyTorch will become much easier.

---

# Python Mastery Notes

# Chapter 2 — Python Memory Model (Objects, References, Identity & Mutability)

---

# Why Should You Learn This?

Consider this code:

```python
a = [1, 2, 3]

b = a

b.append(4)

print(a)
```

Most beginners expect:

```python
[1, 2, 3]
```

Actual Output:

```python
[1, 2, 3, 4]
```

Why?

Because **variables don't contain values—they reference objects**.

Understanding this is one of the biggest differences between a beginner and an experienced Python programmer.

---

# Everything in Python is an Object

Unlike languages like C, **almost everything in Python is an object**.

Examples:

```python
10
```

Integer object.

```python
3.14
```

Float object.

```python
"Hello"
```

String object.

```python
[1, 2, 3]
```

List object.

```python
True
```

Boolean object.

Even this:

```python
print
```

is an object (a function).

Even classes are objects.

---

# What is an Object?

An object has three important properties:

1. Identity
2. Type
3. Value

Example

```python
age = 20
```

The integer object has:

```
Identity → unique memory identity

Type → int

Value → 20
```

---

# Object Identity

Every object has a unique identity.

Python lets us see it using:

```python
id()
```

Example

```python
x = 10

print(id(x))
```

Output (example only):

```
140316955542672
```

Don't memorize the number.

It changes every execution.

---

# Type

Every object has a type.

```python
name = "Sami"

print(type(name))
```

Output

```python
<class 'str'>
```

Examples

```python
print(type(10))
print(type(2.5))
print(type(False))
print(type([1,2]))
print(type((1,2)))
print(type({1,2}))
print(type({"a":1}))
```

Outputs

```
int
float
bool
list
tuple
set
dict
```

---

# Value

Objects store values.

```python
x = 100
```

Value =

```
100
```

---

# Variables are NOT Boxes

Most books teach this:

```
x
│
100
```

This is NOT how Python actually works.

Python is closer to:

```
x
│
▼
+------+
| 100  |
+------+
```

The variable points to the object.

---

# References

Suppose

```python
a = 100
```

Diagram

```
a
│
▼
+------+
| 100  |
+------+
```

Now

```python
b = a
```

Diagram

```
a ──┐
    │
    ▼
+------+
| 100  |
+------+
    ▲
    │
b ──┘
```

There is still **one object**.

Two references.

---

# Example 1

```python
a = 100

b = a

print(a)
print(b)
```

Output

```
100
100
```

Easy.

---

# Example 2

```python
a = 100

b = a

a = 500

print(a)
print(b)
```

Output

```
500
100
```

Why?

Because

```python
a = 500
```

does NOT change the object.

It makes `a` reference another object.

Diagram before:

```
a ──┐
    │
    ▼
+------+
|100|
+------+
    ▲
    │
b ──┘
```

After

```python
a = 500
```

Diagram

```
a
│
▼
+------+
|500|
+------+

b
│
▼
+------+
|100|
+------+
```

---

# Identity Comparison

Use

```python
is
```

Example

```python
a = 10
b = a

print(a is b)
```

Output

```
True
```

Because they refer to the same object.

---

# Equality Comparison

Use

```python
==
```

Example

```python
a = 10
b = 10

print(a == b)
```

Output

```
True
```

`==` compares **values**.

---

# Difference Between `is` and `==`

This is one of the most commonly misunderstood concepts.

Example

```python
a = [1, 2]

b = [1, 2]
```

Now

```python
print(a == b)
```

Output

```
True
```

Because values are equal.

Now

```python
print(a is b)
```

Output

```
False
```

Because they are different list objects.

Diagram

```
a ─────► [1,2]

b ─────► [1,2]
```

Two different objects.

---

# Another Example

```python
a = [1,2]

b = a
```

Diagram

```
a ───┐
     │
     ▼
 [1,2]
     ▲
     │
b ───┘
```

Now

```python
print(a is b)
```

Output

```
True
```

---

# Immutable Objects

Immutable means

> **Cannot change after creation.**

Examples

```python
int

float

bool

str

tuple

frozenset
```

Example

```python
x = 10

x = 20
```

Did we change `10`?

No.

We created a new object.

---

# Mutable Objects

Mutable means

> **Can change after creation.**

Examples

```python
list

dict

set

bytearray
```

Example

```python
numbers = [1,2]

numbers.append(3)
```

The same list object becomes

```
[1,2,3]
```

---

# Visualizing Mutable Objects

```python
a = [1,2]

b = a
```

```
a ──┐
    │
    ▼
+-----------+
| [1,2]     |
+-----------+
    ▲
    │
b ──┘
```

Now

```python
b.append(3)
```

The object itself changes:

```
+--------------+
| [1,2,3]      |
+--------------+
```

Both variables "see" the change.

---

# Example

```python
a = [10,20]

b = a

b.append(30)

print(a)
print(b)
```

Output

```python
[10, 20, 30]
[10, 20, 30]
```

---

# Common Beginner Mistake

Many students think:

```python
b = a
```

creates a copy.

It does **not**.

It creates another reference.

---

# How to Make a Copy

We'll study copying in detail later, but here's a preview:

```python
a = [1,2,3]

b = a.copy()

b.append(4)

print(a)
print(b)
```

Output

```
[1,2,3]
[1,2,3,4]
```

---

# AI/ML Connection

Suppose you're preprocessing a dataset:

```python
train_data = original_data
```

If you modify `train_data`, you may accidentally modify `original_data` too, because both names reference the same object.

A safer approach is often to create a copy (the exact method depends on the object type):

```python
train_data = original_data.copy()
```

This concept becomes extremely important when working with lists, dictionaries, NumPy arrays, and Pandas DataFrames.

---

# Memory Quiz

### Predict the Output

```python
a = [1]

b = a

b.append(2)

print(a)
```

---

### Predict the Output

```python
a = 100

b = a

a = 200

print(b)
```

---

### Predict the Output

```python
a = [1,2]

b = [1,2]

print(a == b)

print(a is b)
```

---

# Summary

| Concept   | Meaning                                  |
| --------- | ---------------------------------------- |
| Object    | A value with identity, type, and value   |
| Variable  | A reference (name) pointing to an object |
| `id()`    | Returns an object's identity             |
| `type()`  | Returns an object's type                 |
| `==`      | Compares values                          |
| `is`      | Compares object identity                 |
| Immutable | Cannot be changed after creation         |
| Mutable   | Can be changed after creation            |
| `b = a`   | Creates another reference, not a copy    |

---

# Practice (Do This Before the Next Lesson)

Without running the code, predict the output of each:

```python
# Question 1
a = 5
b = a
a = 10
print(a, b)
```

```python
# Question 2
a = [1, 2]
b = a
a.append(3)
print(b)
```

```python
# Question 3
a = [1, 2]
b = [1, 2]
print(a == b)
print(a is b)
```

```python
# Question 4
a = "Python"
b = a
print(a is b)
```


