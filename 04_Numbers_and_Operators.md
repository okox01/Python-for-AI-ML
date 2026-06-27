
---

# Python Mastery Notes

# Chapter 4 — Operators (Complete Master Guide)

---

# What is an Operator?

An **operator** is a symbol or keyword that tells Python to perform an operation on one or more operands.

Example:

```python
10 + 5
```

Here:

```text
10      → Operand
+       → Operator
5       → Operand
```

Result:

```text
15
```

---

# Types of Operators in Python

Python has seven major categories:

| Category   | Operators                  |
| ---------- | -------------------------- |
| Arithmetic | `+ - * / // % **`          |
| Assignment | `= += -= *= /= //= %= **=` |
| Comparison | `== != > < >= <=`          |
| Logical    | `and or not`               |
| Identity   | `is is not`                |
| Membership | `in not in`                |
| Bitwise    | `& \| ^ ~ << >>`           |

We'll master each one.

---

# 1. Arithmetic Operators

These perform mathematical operations.

| Operator | Meaning        | Example  |
| -------- | -------------- | -------- |
| `+`      | Addition       | `5 + 2`  |
| `-`      | Subtraction    | `5 - 2`  |
| `*`      | Multiplication | `5 * 2`  |
| `/`      | Division       | `5 / 2`  |
| `//`     | Floor Division | `5 // 2` |
| `%`      | Modulus        | `5 % 2`  |
| `**`     | Power          | `5 ** 2` |

---

## Addition

```python
a = 10
b = 20

print(a + b)
```

Output

```text
30
```

---

## Addition with Strings

The `+` operator also concatenates strings.

```python
first = "Machine"
second = "Learning"

print(first + " " + second)
```

Output

```text
Machine Learning
```

---

## Addition with Lists

```python
a = [1,2]
b = [3,4]

print(a + b)
```

Output

```text
[1,2,3,4]
```

Notice that lists are **joined**, not added numerically.

---

## Multiplication

Numbers

```python
print(5 * 4)
```

Output

```text
20
```

Strings

```python
print("AI " * 3)
```

Output

```text
AI AI AI
```

Lists

```python
print([1,2] * 3)
```

Output

```text
[1,2,1,2,1,2]
```

---

# Division

```python
print(10 / 2)
```

Output

```text
5.0
```

Notice:

The result is always a float.

Even

```python
print(20 / 5)
```

returns

```text
4.0
```

---

# Modulus

Useful for checking even or odd numbers.

```python
number = 18

print(number % 2)
```

Output

```text
0
```

Even number.

---

# Power

```python
print(3 ** 4)
```

Output

```text
81
```

Useful in mathematics and machine learning.

---

# 2. Assignment Operators

Basic assignment

```python
x = 10
```

Python also supports compound assignment.

---

## Addition Assignment

Instead of

```python
x = x + 5
```

write

```python
x += 5
```

Example

```python
x = 10

x += 5

print(x)
```

Output

```text
15
```

---

## Subtraction Assignment

```python
x = 20

x -= 4

print(x)
```

Output

```text
16
```

---

## Multiplication Assignment

```python
x = 10

x *= 3

print(x)
```

Output

```text
30
```

---

## Division Assignment

```python
x = 20

x /= 4

print(x)
```

Output

```text
5.0
```

---

## Floor Division Assignment

```python
x = 15

x //= 2

print(x)
```

Output

```text
7
```

---

## Power Assignment

```python
x = 3

x **= 3

print(x)
```

Output

```text
27
```

---

# 3. Comparison Operators

Comparison operators always return a Boolean (`True` or `False`).

---

## Equal (`==`)

```python
print(5 == 5)
```

Output

```text
True
```

---

## Not Equal (`!=`)

```python
print(5 != 3)
```

Output

```text
True
```

---

## Greater Than (`>`)

```python
print(10 > 8)
```

Output

```text
True
```

---

## Less Than (`<`)

```python
print(3 < 7)
```

Output

```text
True
```

---

## Greater Than or Equal (`>=`)

```python
print(5 >= 5)
```

Output

```text
True
```

---

## Less Than or Equal (`<=`)

```python
print(4 <= 8)
```

Output

```text
True
```

---

# Chained Comparisons

Python allows chaining.

```python
age = 20

print(18 <= age <= 30)
```

Output

```text
True
```

Instead of

```python
age >= 18 and age <= 30
```

This is one of Python's cleanest features.

---

# 4. Logical Operators

There are three logical operators.

```text
and
or
not
```

---

## `and`

Returns `True` only if **both** conditions are true.

```python
age = 22
has_id = True

print(age >= 18 and has_id)
```

Output

```text
True
```

Truth table:

| A     | B     | A and B |
| ----- | ----- | ------- |
| True  | True  | True    |
| True  | False | False   |
| False | True  | False   |
| False | False | False   |

---

## `or`

Returns `True` if **at least one** condition is true.

```python
is_admin = False
is_teacher = True

print(is_admin or is_teacher)
```

Output

```text
True
```

---

## `not`

Reverses a Boolean.

```python
logged_in = True

print(not logged_in)
```

Output

```text
False
```

---

# Short-Circuit Evaluation

Python stops evaluating as soon as it already knows the result.

Example:

```python
x = 10

print(x > 5 or x / 0 > 1)
```

Output:

```text
True
```

Why no error?

Because:

```python
x > 5
```

is already `True`, so Python never evaluates:

```python
x / 0
```

Similarly:

```python
x = 2

print(x > 5 and x / 0 > 1)
```

Output:

```text
False
```

Again, no error.

This behavior is called **short-circuit evaluation**.

---

# 5. Identity Operators

You learned these in the previous chapter.

```python
a = [1,2]

b = a

print(a is b)
```

Output

```text
True
```

```python
c = [1,2]

print(a is c)
```

Output

```text
False
```

Remember:

* `==` → compares values
* `is` → compares identities

---

# 6. Membership Operators

Check whether an item exists in a collection.

```python
languages = ["Python", "Java", "C++"]

print("Python" in languages)
```

Output

```text
True
```

---

```python
print("Rust" not in languages)
```

Output

```text
True
```

Useful in:

* Lists
* Tuples
* Strings
* Dictionaries (checks keys)

Example:

```python
student = {
    "name": "Sami",
    "cgpa": 3.9
}

print("name" in student)
```

Output:

```text
True
```

---

# 7. Bitwise Operators (Preview)

These work on the binary representation of integers.

```python
&
|
^
~
<<
>>
```

Example:

```python
print(5 & 3)
```

Output:

```text
1
```

We'll cover them in detail in an advanced chapter because they're less common in day-to-day AI/ML work.

---

# Operator Precedence

Python follows an order of operations, similar to mathematics.

From highest to lower (simplified):

1. `()`
2. `**`
3. Unary `+`, `-`, `not`
4. `*`, `/`, `//`, `%`
5. `+`, `-`
6. Comparisons (`<`, `==`, etc.)
7. `not`
8. `and`
9. `or`

Example:

```python
print(2 + 3 * 4)
```

Output:

```text
14
```

because multiplication happens first.

Use parentheses when it makes the code easier to read:

```python
print((2 + 3) * 4)
```

Output:

```text
20
```

---

# Real AI/ML Examples

## Training Loop

```python
epochs = 100

current_epoch = 50

print(current_epoch < epochs)
```

---

## Accuracy Check

```python
accuracy = 0.94

print(accuracy >= 0.90)
```

---

## Learning Rate Update

```python
learning_rate = 0.01

learning_rate *= 0.1

print(learning_rate)
```

Output:

```text
0.001
```

---

## Dataset Check

```python
features = ["age", "salary", "height"]

print("salary" in features)
```

---

# Common Beginner Mistakes

### Mistake 1

Using `=` instead of `==`

Wrong:

```python
if x = 5:
    print("Hello")
```

`=` assigns a value; it does not compare.

Correct:

```python
if x == 5:
    print("Hello")
```

---

### Mistake 2

Using `is` to compare numbers or strings.

Wrong:

```python
a = 1000
b = 1000

print(a is b)
```

Use:

```python
print(a == b)
```

Use `is` primarily when checking identity, especially with `None`:

```python
if model is None:
    print("No model loaded.")
```

---

### Mistake 3

Forgetting precedence.

```python
print(2 + 3 * 4)
```

Many beginners answer `20`.

The correct answer is `14`.

---

# Practice Questions

Predict the output without running the code:

```python
print(10 % 3)
```

```python
print(2 ** 5)
```

```python
print(5 == 5 and 10 > 20)
```

```python
print("Py" * 3)
```

```python
print("AI" in "Artificial Intelligence")
```

```python
a = [1]
b = [1]

print(a == b)
print(a is b)
```

```python
x = 5
x += 10
print(x)
```

```python
print(not False or False)
```

---

# Mini Project

Write a simple eligibility checker:

```python
age = 20
cgpa = 3.6
has_id = True

eligible = (age >= 18) and (cgpa >= 3.0) and has_id

print("Eligible:", eligible)
```

Try changing the values and predicting the output before running the program.

---

# Chapter Summary

| Operator Type | Purpose                      |
| ------------- | ---------------------------- |
| Arithmetic    | Perform calculations         |
| Assignment    | Store and update values      |
| Comparison    | Compare values               |
| Logical       | Combine or negate conditions |
| Identity      | Compare object identities    |
| Membership    | Test if an element exists    |
| Bitwise       | Manipulate bits              |

## Key Takeaways

* Use `==` for value comparison and `is` for identity comparison.
* Understand **short-circuit evaluation**; it improves both performance and safety.
* Learn operator precedence, but don't hesitate to use parentheses for clarity.
* Compound assignment operators (`+=`, `*=`, etc.) make code cleaner.
* Logical operators are used constantly in data validation, model evaluation, and control flow.

---


