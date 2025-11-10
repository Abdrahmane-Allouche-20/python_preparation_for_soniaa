# Python Study Guide – Programmation Module (First Year CS, Belgium)

## Table of Contents
1. [Python Basics](#python-basics)
2. [Variables & Types](#variables--types)
3. [Input / Output, Comments, Indentation](#input--output-comments-indentation)
4. [Operators](#operators)
5. [Control Flow](#control-flow)
6. [Functions](#functions)
7. [Data Structures](#data-structures)
8. [Strings](#strings)
9. [File Handling](#file-handling)
10. [Exceptions](#exceptions)
11. [Modules & Imports](#modules--imports)
12. [Object-Oriented Basics](#object-oriented-basics)
13. [Example Programs](#example-programs)
14. [Common Exam/QCM Traps](#common-examqcm-traps)
15. [Mini QCM Practice (100 Questions)](#mini-qcm-practice-100-questions)
16. [Final Summary](#final-summary)

---

## Python Basics

- Python is an interpreted, high-level, general-purpose programming language.
- Code is executed line by line.
- Python files use the `.py` extension.

```python
# This is a comment, Python ignores this line
print("Hello, World!")  # Output: Hello, World!
```

**Summary:**  
Python is simple, readable, and follows strict indentation rules.

---

## Variables & Types

### Variables
- Created by assigning a value.
- No need to declare a type before assignment.

```python
x = 5
y = 3.14
name = "Alice"
is_valid = True
```

### Types:
- `int` - Integer numbers
- `float` - Decimal numbers
- `str` - Text/strings
- `bool` - True or False

```python
a = 10          # int
b = 2.5         # float
c = "Hello"     # str
d = False       # bool
```

**Type conversion:**

```python
# Convert int to float
a = 5
b = float(a)       # 5.0

# Convert str to int (if possible)
s = "12"
num = int(s)       # 12

# Convert between types
str_num = str(num) # "12"
```

**Summary:**  
Variables store data. Python automatically detects the type. Explicit conversion is possible using int(), float(), str(), bool().

---

## Input / Output, Comments, Indentation

- `input()` to take user input (returns string).
- `print()` to display output.

```python
name = input("What is your name? ")
print("Hello, " + name)
```

### Comments
- Start with `#`.

### Indentation
- Use 4 spaces per indentation level.
- Indentation defines code blocks (not curly braces like C/Java).

```python
if True:
    print("Indented!")  # Inside 'if' block
print("Out!")  # Outside block
```

**Summary:**  
Always keep indentation consistent. Comments start with #.

---

## Operators

### Arithmetic Operators
- `+` Addition
- `-` Subtraction
- `*` Multiplication
- `/` Division (float)
- `//` Integer division
- `%` Modulus (remainder)
- `**` Exponentiation

```python
a = 10
b = 3
print(a + b, a - b, a * b, a / b, a // b, a % b, a ** b)
```

### Comparison Operators
- `==` Equal to
- `!=` Not equal to
- `<` Less than
- `>` Greater than
- `<=` Less than/Equal to
- `>=` Greater than/Equal to

### Logical Operators
- `and`, `or`, `not`

```python
x = 5
print(x > 2 and x < 10)     # True
print(not (x < 5))          # True
```

### Assignment Operators
- `=`, `+=`, `-=`, `*=`, `/=`, `//=`, `%=`, `**=`

```python
x = 5
x += 3     # x = x + 3, so x = 8
```

### Membership Operators
- `in`, `not in`

```python
mylist = [1, 2, 3]
print(2 in mylist)      # True
print(4 not in mylist)  # True
```

### Identity Operators
- `is`, `is not`

```python
a = [1,2]
b = a
print(a is b)        # True (same object)
c = [1,2]
print(a is c)        # False (different objects, same value)
```

**Summary:**  
Operators perform calculations, comparisons, and logic.

---

## Control Flow

### if / elif / else

```python
x = 10
if x > 10:
    print("Greater")
elif x == 10:
    print("Equal")
else:
    print("Smaller")
```

### while Loops

```python
i = 0
while i < 5:
    print(i)
    i += 1
```

### for Loops

```python
for number in [1,2,3]:
    print(number)
    
for i in range(5):    # 0 to 4
    print(i)
```

### break, continue, pass

- **break:** Exit loop now.
- **continue:** Go to next loop iteration.
- **pass:** Do nothing (placeholder).

```python
for i in range(5):
    if i == 3:
        break
    print(i)    # Prints 0,1,2

for i in range(5):
    if i == 3:
        continue
    print(i)    # Prints 0,1,2,4

for i in range(5):
    pass    # Does nothing (usually used to define empty loops/functions)
```

**Summary:**  
Use if/elif/else for decisions. while/for for repetition.

---

## Functions

### Defining Functions

```python
def greet(name):
    print("Hello, " + name)
```

### Parameters & Return Values

```python
def add(a, b):
    return a + b

sum = add(2, 3)
print(sum)
```

### Scope

- **Local variables:** Defined inside function, only accessible there.
- **Global variables:** Defined outside all functions.

```python
x = 10  # global
def foo():
    y = 5  # local
    print(x, y)   # prints 10, 5
foo()
```

**To modify a global variable inside a function:**

```python
total = 0
def add():
    global total
    total += 1
```

### Built-in Functions

- `len()` – length
- `range()` – sequence of numbers
- `type()` – returns type
- `print()`, `input()`, `sum()`, `max()`, `min()`, `abs()`, `sorted()`, `reversed()`

```python
nums = [1,2,3]
print(len(nums))                # 3
print(range(5))                 # 0,1,2,3,4
print(type("hello"))            # <class 'str'>
print(sum([1,2,3]), max([1,2,3]))
```

**Summary:**  
Functions organize code. Use return to pass values. Scope matters for variables.

---

## Data Structures

### Lists

- Ordered, mutable, can contain any types.

```python
fruits = ["apple", "banana", "cherry"]
fruits[0] = "orange"
for fruit in fruits:
    print(fruit)
```

### Tuples

- Ordered, immutable.

```python
point = (3, 5)
print(point[0])
```

### Sets

- Unordered, unique elements.

```python
s = set([1, 2, 3, 3])
print(s)    # {1, 2, 3}
```

### Dictionaries

- Key-value pairs, unordered, mutable.

```python
person = {"name": "Alice", "age": 20}
print(person["name"])
person["age"] = 21
for key in person:
    print(key, person[key])
```

**Access/Modify/Iterate:**

- **List:** `l[1]`, `l.append(x)`
- **Tuple:** `t[1]`
- **Set:** `s.add(x)`
- **Dict:** `d[key]`

**Summary:**  
Lists/tuples: ordered, sets/dicts: unordered. Use right structure for the job.

---

## Strings

- Immutable sequences of characters.

```python
s = "Python"
print(s[0])          # 'P'
print(s[1:4])        # 'yth'
```

### Methods

- `upper()`, `lower()`, `strip()`, `replace()`, `find()`, `split()`, `join()`

```python
s = " Hello World "
print(s.strip())                   # 'Hello World'
print(s.replace("Hello", "Hi"))    # ' Hi World '
print(s.split())                   # ['Hello', 'World']
print("-".join(['a','b']))         # 'a-b'
```

### f-Strings (Formatting)

```python
name = "Alice"
age = 20
print(f"My name is {name} and I am {age}")
```

**Summary:**  
Strings are everywhere in Python. Use methods for manipulation, f-strings for formatting.

---

## File Handling

- **Open:** `open(filename, mode)`
  - 'r': read, 'w': write (overwrite), 'a': append

```python
# Writing to file
f = open("myfile.txt", "w")
f.write("Hello World!")
f.close()

# Reading from file
f = open("myfile.txt", "r")
content = f.read()
f.close()
print(content)
```

- Use `with` for automatic closing:

```python
with open("myfile.txt", "r") as f:
    data = f.read()
```

**Summary:**  
Always close files; use `with open()` for safety.

---

## Exceptions

- Catch and handle errors.

```python
try:
    num = int(input("Enter a number: "))
    print(10/num)
except ValueError:
    print("Not a number!")
except ZeroDivisionError:
    print("Cannot divide by zero!")
finally:
    print("Done")
```

**Summary:**  
Try/except helps handle unexpected errors. Always use for risky operations.

---

## Modules & Imports

- Split code into files/modules.
- Use built-in modules for extra functionality.

```python
import math
print(math.sqrt(25))

import random
print(random.randint(1, 10))

from datetime import datetime
print(datetime.now())
```

**Summary:**  
Import modules to reuse code or access standard features.

---

## Object-Oriented Basics

```python
class Dog:
    def __init__(self, name):
        self.name = name
    def bark(self):
        print(f"{self.name} says woof!")

d = Dog("Rex")
d.bark()
```

- **Class**: Blueprint for objects.
- **self**: Refers to the object itself.

**Summary:**  
OOP lets you create your own types. Each class can hold data and functions.

---

## Example Programs

### 1. Print Even Numbers 1-10

```python
for i in range(1, 11):
    if i % 2 == 0:
        print(i)
```

### 2. Find the Largest Number in a List

```python
nums = [3, 7, 2, 9]
largest = max(nums)
print(largest)
```

### 3. Counting Words in a String

```python
s = "hello world python"
words = s.split()
print(len(words))
```

---

## Common Exam/QCM Traps

- **Indentation Error:** Forgetting or misaligning spaces.
- **Type Conversion:** Using int() on a non-numeric string leads to ValueError.
- **List vs. Tuple:** Lists can be changed, tuples cannot.
- **Assignment vs. Comparison:** `=` vs. `==`
- **Loop range:** `range(5)` is 0..4, not 1..5.
- **String immutability:** `s[0] = 'P'` raises error.
- **KeyError:** Accessing missing key in dict.
- **File not closed:** Not using `.close()` or `with open()`.
- **Global scope:** Modifying global variable needs `global`.
- **break/continue:** They change loop flow.

---

## Mini QCM Practice (100 Questions)

**Below are 100 multiple choice questions covering the essentials.**

[100 Python MCQ (QCM) Questions and Answers](./python_qcm_100.md)



---

## Final Summary

- Python is simple, readable, and great for beginners.
- Focus on understanding how data types, control flow, functions, and data structures work.
- Review example programs and MCQ – knowing tricky details helps for QCM-style exams!
- Practice by running code and reviewing common errors.
- Good luck – you’ve got this!

---

_Convert this Markdown file to PDF using Typora, pandoc, or any online tool. Syntax highlighting and headings will remain intact._
