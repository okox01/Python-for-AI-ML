
---

# Python Mastery Notes

# Chapter 5 — Strings (Part 1: Fundamentals)

---

# What is a String?

A **string** is a sequence of Unicode characters.

Examples:

```python
"Hello"

"Python"

"123"

"😊"

"Machine Learning"
```

A string can contain:

* Letters
* Numbers
* Spaces
* Symbols
* Emojis
* Unicode characters from almost every language

---

# Real-Life Analogy

Imagine a train.

```
+---+---+---+---+---+
| H | e | l | l | o |
+---+---+---+---+---+
```

Each compartment contains one character.

Python stores a string similarly—as an ordered sequence of characters.

---

# Creating Strings

## Method 1 — Single Quotes

```python
name = 'Sami'
```

---

## Method 2 — Double Quotes

```python
name = "Sami"
```

Both are identical.

```python
print(type(name))
```

Output

```text
<class 'str'>
```

---

## Method 3 — Triple Quotes

Used for multi-line strings.

```python
paragraph = """
Python
Machine Learning
Artificial Intelligence
"""

print(paragraph)
```

Output

```text
Python
Machine Learning
Artificial Intelligence
```

---

# Which Quotes Should You Use?

Suppose your sentence contains an apostrophe.

Wrong:

```python
name = 'I'm Sami'
```

Python thinks the string ends after `I`.

Correct:

```python
name = "I'm Sami"
```

Or escape the apostrophe:

```python
name = 'I\'m Sami'
```

---

# Empty String

```python
text = ""

print(text)
```

Length:

```python
print(len(text))
```

Output

```text
0
```

---

# String is an Object

```python
name = "Python"

print(type(name))
print(id(name))
```

Like every other Python value, a string is an object.

---

# String Indexing

Every character has an index.

Example:

```python
language = "Python"
```

```
Character

 P   y   t   h   o   n

Index

 0   1   2   3   4   5
```

---

## Accessing Characters

```python
language = "Python"

print(language[0])
```

Output

```text
P
```

---

```python
print(language[3])
```

Output

```text
h
```

---

```python
print(language[5])
```

Output

```text
n
```

---

# Negative Indexing

Python also counts from the end.

```
 P  y  t  h  o  n

-6 -5 -4 -3 -2 -1
```

Example

```python
language = "Python"

print(language[-1])
```

Output

```text
n
```

---

```python
print(language[-2])
```

Output

```text
o
```

---

```python
print(language[-6])
```

Output

```text
P
```

---

# Why Negative Indexing?

Suppose you only need the last character.

Instead of

```python
language[len(language)-1]
```

Simply write

```python
language[-1]
```

Much cleaner.

---

# Index Out of Range

```python
language = "Python"

print(language[100])
```

Output

```text
IndexError: string index out of range
```

Always ensure the index is valid.

---

# Length of String

Use

```python
len()
```

Example

```python
language = "Python"

print(len(language))
```

Output

```text
6
```

---

# Practical Example

```python
password = "OpenAI123"

print(len(password))
```

Output

```text
9
```

Useful for password validation.

---

# String Slicing

Probably the most important feature.

Syntax

```python
string[start:stop]
```

Remember:

* Start included
* Stop excluded

---

Example

```python
language = "Python"

print(language[0:2])
```

Output

```text
Py
```

Python takes:

```
0 → P

1 → y
```

Stops before index 2.

---

Another Example

```python
print(language[2:5])
```

Output

```text
tho
```

---

# Omitting Start

```python
print(language[:3])
```

Output

```text
Pyt
```

Means

```
Start from beginning.
```

---

# Omitting Stop

```python
print(language[2:])
```

Output

```text
thon
```

Means

```
Go until the end.
```

---

# Entire String

```python
print(language[:])
```

Output

```text
Python
```

---

# Step in Slicing

Syntax

```python
string[start:stop:step]
```

Example

```python
language = "Python"

print(language[0:6:2])
```

Output

```text
Pto
```

Indexes selected:

```
0

2

4
```

---

Another Example

```python
print(language[::2])
```

Output

```text
Pto
```

---

# Reverse String

One of Python's coolest features.

```python
language = "Python"

print(language[::-1])
```

Output

```text
nohtyP
```

Step =

```text
-1
```

Means move backwards.

---

# Copy String

```python
copy = language[:]
```

This creates another string object with the same content. Since strings are immutable, copying is rarely necessary.

---

# String Immutability (Very Important)

Strings **cannot be modified** after creation.

Example

```python
language = "Python"

language[0] = "J"
```

Output

```text
TypeError
```

---

Why?

Because strings are immutable.

Instead

```python
language = "J" + language[1:]

print(language)
```

Output

```text
Jython
```

---

# Why Are Strings Immutable?

Benefits include:

* Faster comparisons
* Safer sharing between variables
* Hashable (usable as dictionary keys)
* Reliable behavior

---

# Iterating Through a String

Using a `for` loop:

```python
word = "AI"

for ch in word:
    print(ch)
```

Output

```text
A
I
```

Using indexes:

```python
word = "Python"

for i in range(len(word)):
    print(i, word[i])
```

Output

```text
0 P
1 y
2 t
3 h
4 o
5 n
```

---

# Membership

Check whether a substring exists.

```python
text = "Machine Learning"

print("Machine" in text)
```

Output

```text
True
```

---

```python
print("Python" in text)
```

Output

```text
False
```

---

# String Concatenation

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

# String Repetition

```python
print("AI " * 5)
```

Output

```text
AI AI AI AI AI
```

---

# Escape Characters

Sometimes special characters need escaping.

| Escape | Meaning      |
| ------ | ------------ |
| `\n`   | New line     |
| `\t`   | Tab          |
| `\\`   | Backslash    |
| `\"`   | Double quote |
| `\'`   | Single quote |

Example

```python
print("Hello\nWorld")
```

Output

```text
Hello
World
```

---

Example

```python
print("Name\tAge")
```

Output

```text
Name    Age
```

---

# Raw Strings

Useful for Windows paths and regular expressions.

Without raw string:

```python
path = "C:\new\test"
print(path)
```

This is **not** interpreted as you might expect because `\n` becomes a newline and `\t` becomes a tab.

Correct:

```python
path = r"C:\new\test"

print(path)
```

Output

```text
C:\new\test
```

---

# AI/ML Example

Suppose you receive text from users.

```python
sentence = "  I Love Python and AI  "
```

Later we'll clean it using string methods such as:

* `strip()`
* `lower()`
* `replace()`
* `split()`

Text preprocessing begins with string manipulation.

---

# Common Beginner Mistakes

### Mistake 1

```python
name = "Python"

name[0] = "J"
```

❌ Error.

Strings are immutable.

---

### Mistake 2

```python
text = "Python"

print(text[6])
```

❌ Index out of range.

Valid indexes:

```
0–5
```

---

### Mistake 3

```python
print("Hello" + 5)
```

❌ Error.

Correct:

```python
print("Hello" + str(5))
```

Output

```text
Hello5
```

---

# Practice Questions

Predict the output:

```python
text = "Python"

print(text[-1])
```

---

```python
text = "Machine"

print(text[1:5])
```

---

```python
text = "Learning"

print(text[::-1])
```

---

```python
print(len("Artificial"))
```

---

```python
print("AI" * 4)
```

---

```python
print("Python"[:4])
```

---

```python
print("Python"[2:])
```

---

```python
print("Data" in "Data Science")
```

---

# Mini Project

Extract information from a filename:

```python
filename = "model_v1.pkl"

print("First character:", filename[0])
print("Last character:", filename[-1])
print("Extension:", filename[-3:])
print("Length:", len(filename))
print("Contains 'model':", "model" in filename)
```

---

# Chapter Summary

| Concept          | Description                                       |
| ---------------- | ------------------------------------------------- |
| String           | Immutable sequence of Unicode characters          |
| Indexing         | Access a single character                         |
| Slicing          | Extract part of a string                          |
| Negative Index   | Count from the end                                |
| `len()`          | Returns string length                             |
| `in`             | Checks for membership                             |
| `+`              | Concatenates strings                              |
| `*`              | Repeats strings                                   |
| Escape Sequences | Special characters like `\n` and `\t`             |
| Raw Strings      | Prevent backslashes from being treated as escapes |

---


---

# Python Mastery Notes

# Chapter 6 — String Methods (Part 2)

---

# What is a Method?

A **method** is a function that belongs to an object.

Example:

```python
name = "python"

print(name.upper())
```

Here:

```text
name      → String object

upper()   → Method
```

Think of it like this:

```
Human
 ├── walk()
 ├── sleep()
 └── eat()

String
 ├── upper()
 ├── lower()
 ├── replace()
 └── split()
```

Methods are simply actions an object can perform.

---

# Important Rule

**Strings are immutable.**

That means almost every string method:

* Returns a **new string**
* Does **not** modify the original string

Example:

```python
text = "python"

text.upper()

print(text)
```

Output

```text
python
```

Why?

Because `upper()` created a **new string**, but we ignored it.

Correct:

```python
text = text.upper()

print(text)
```

Output

```text
PYTHON
```

This is one of the biggest beginner mistakes.

---

# 1. upper()

Converts every lowercase letter into uppercase.

```python
text = "python"

print(text.upper())
```

Output

```text
PYTHON
```

---

AI Example

```python
command = "train"

if command.upper() == "TRAIN":
    print("Training Started")
```

Users may type:

```
train
TRAIN
Train
tRaIn
```

Using `upper()` lets you compare them consistently.

---

# 2. lower()

Converts every uppercase letter into lowercase.

```python
text = "PYTHON"

print(text.lower())
```

Output

```text
python
```

---

Real AI Example

```python
sentence = "I LOVE PYTHON"

clean = sentence.lower()

print(clean)
```

Output

```text
i love python
```

Most NLP preprocessing begins with converting text to lowercase.

---

# 3. capitalize()

Only the first character becomes uppercase.

```python
text = "python programming"

print(text.capitalize())
```

Output

```text
Python programming
```

---

# 4. title()

Capitalizes every word.

```python
text = "machine learning with python"

print(text.title())
```

Output

```text
Machine Learning With Python
```

Useful for headings.

---

# 5. swapcase()

Changes lowercase ↔ uppercase.

```python
text = "PyThOn"

print(text.swapcase())
```

Output

```text
pYtHoN
```

---

# 6. strip()

Removes spaces from both ends.

```python
text = "   Python   "

print(text.strip())
```

Output

```text
Python
```

Notice:

Spaces inside remain.

```
"Machine   Learning"
```

becomes

```
"Machine   Learning"
```

Only the ends are cleaned.

---

AI Example

Users often enter:

```
"   Hello ChatGPT    "
```

Before saving:

```python
message = message.strip()
```

---

# 7. lstrip()

Left side only.

```python
text = "     Python"

print(text.lstrip())
```

Output

```text
Python
```

---

# 8. rstrip()

Right side only.

```python
text = "Python     "

print(text.rstrip())
```

Output

```text
Python
```

---

# 9. replace()

One of the most useful methods.

```python
text = "I love Java"

print(text.replace("Java", "Python"))
```

Output

```text
I love Python
```

---

Replace all occurrences

```python
text = "AI AI AI"

print(text.replace("AI", "ML"))
```

Output

```text
ML ML ML
```

---

Replace only one occurrence

```python
text = "AI AI AI"

print(text.replace("AI", "ML", 1))
```

Output

```text
ML AI AI
```

The third argument is the maximum number of replacements.

---

# 10. split()

Extremely important.

Converts one string into a list.

```python
text = "Python Java C++"

print(text.split())
```

Output

```text
['Python', 'Java', 'C++']
```

---

Split by comma

```python
text = "Apple,Banana,Mango"

print(text.split(","))
```

Output

```text
['Apple', 'Banana', 'Mango']
```

---

Real AI Example

Sentence:

```
I love machine learning
```

After

```python
words = sentence.split()
```

Result

```
["I","love","machine","learning"]
```

This process is called **tokenization** (a simple form).

---

# 11. join()

The opposite of `split()`.

List → String

```python
words = ["Machine", "Learning"]

print(" ".join(words))
```

Output

```text
Machine Learning
```

---

Comma separated

```python
items = ["Apple","Banana","Orange"]

print(",".join(items))
```

Output

```text
Apple,Banana,Orange
```

---

AI Example

Suppose you predict words:

```
["I","love","AI"]
```

Convert back

```python
sentence = " ".join(words)
```

---

# 12. find()

Returns the index of the first match.

```python
text = "Machine Learning"

print(text.find("Learning"))
```

Output

```text
8
```

---

If not found

```python
print(text.find("Python"))
```

Output

```text
-1
```

No error occurs.

---

# 13. index()

Similar to `find()`.

Difference:

If not found

```python
text.index("Python")
```

Produces

```text
ValueError
```

---

Comparison

```
find()

Not Found → -1
```

```
index()

Not Found → Error
```

Use `find()` when a missing value is expected and not exceptional.

---

# 14. startswith()

```python
text = "Machine Learning"

print(text.startswith("Machine"))
```

Output

```text
True
```

---

# 15. endswith()

```python
filename = "model.pkl"

print(filename.endswith(".pkl"))
```

Output

```text
True
```

Very common when checking file extensions.

---

# 16. count()

Counts occurrences.

```python
text = "banana"

print(text.count("a"))
```

Output

```text
3
```

---

# 17. isalpha()

Only letters.

```python
print("Python".isalpha())
```

Output

```text
True
```

---

```python
print("Python123".isalpha())
```

Output

```text
False
```

---

# 18. isdigit()

```python
print("12345".isdigit())
```

Output

```text
True
```

---

```python
print("12A".isdigit())
```

Output

```text
False
```

---

# 19. isalnum()

Letters OR numbers.

```python
print("Python123".isalnum())
```

Output

```text
True
```

---

```python
print("Python 123".isalnum())
```

Output

```text
False
```

Space is not alphanumeric.

---

# 20. islower()

```python
print("python".islower())
```

Output

```text
True
```

---

# 21. isupper()

```python
print("PYTHON".isupper())
```

Output

```text
True
```

---

# 22. istitle()

```python
print("Machine Learning".istitle())
```

Output

```text
True
```

---

# 23. center()

Centers text.

```python
print("AI".center(10))
```

Output

```text
    AI
```

Useful for console formatting.

---

# 24. zfill()

Pads numbers with leading zeros.

```python
print("25".zfill(5))
```

Output

```text
00025
```

Useful for invoice numbers, IDs, and filenames.

---

# Real AI Pipeline Example

Imagine you receive this user input:

```python
text = "   I LOVE Python!!!   "
```

Clean it step by step:

```python
text = text.strip()
text = text.lower()

print(text)
```

Output

```text
i love python!!!
```

Then:

```python
words = text.split()

print(words)
```

Output

```text
['i', 'love', 'python!!!']
```

This kind of preprocessing is performed before training many NLP models.

---

# Common Beginner Mistakes

## Mistake 1

```python
text.upper()

print(text)
```

Output:

Still lowercase.

Always assign the returned value if you want to keep the change.

---

## Mistake 2

```python
text.split(",")

print(text)
```

`split()` returns a new list; it does not change the original string.

---

## Mistake 3

```python
text.replace("Python","AI")

print(text)
```

Again, `replace()` returns a new string. The original remains unchanged unless you assign it.

---

# Mini Project

Clean user input:

```python
user_text = "   I LOVE Machine Learning With PYTHON   "

clean = user_text.strip()
clean = clean.lower()

words = clean.split()

print(clean)
print(words)
print(len(words))
```

Output:

```text
i love machine learning with python
['i', 'love', 'machine', 'learning', 'with', 'python']
6
```

---

# Practice Questions

Predict the output:

```python
print("python".upper())
```

```python
print("PYTHON".lower())
```

```python
print(" Machine ".strip())
```

```python
print("apple,banana".split(","))
```

```python
print("-".join(["A","B","C"]))
```

```python
print("banana".count("a"))
```

```python
print("123".isdigit())
```

```python
print("Python123".isalnum())
```

```python
print("model.pkl".endswith(".pkl"))
```

```python
print("Machine Learning".find("Learning"))
```

---

# Chapter Summary

| Method         | Purpose                                 |
| -------------- | --------------------------------------- |
| `upper()`      | Convert to uppercase                    |
| `lower()`      | Convert to lowercase                    |
| `capitalize()` | Capitalize first letter                 |
| `title()`      | Capitalize each word                    |
| `swapcase()`   | Reverse case                            |
| `strip()`      | Remove spaces from both ends            |
| `lstrip()`     | Remove left spaces                      |
| `rstrip()`     | Remove right spaces                     |
| `replace()`    | Replace text                            |
| `split()`      | Convert string to list                  |
| `join()`       | Convert list to string                  |
| `find()`       | Find substring (`-1` if absent)         |
| `index()`      | Find substring (raises error if absent) |
| `startswith()` | Check prefix                            |
| `endswith()`   | Check suffix                            |
| `count()`      | Count occurrences                       |
| `isalpha()`    | Letters only                            |
| `isdigit()`    | Digits only                             |
| `isalnum()`    | Letters and/or digits only              |
| `islower()`    | Check lowercase                         |
| `isupper()`    | Check uppercase                         |
| `istitle()`    | Check title case                        |
| `center()`     | Center text                             |
| `zfill()`      | Pad with leading zeros                  |

---




