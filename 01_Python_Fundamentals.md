# 01 - Python Fundamentals

> **Goal:** Build a strong Python foundation for Backend, AI, LLM, and Agentic AI interviews.

---

# Table of Contents

1. Why Python?
2. Python Installation
3. Python Execution Flow
4. Variables
5. Data Types
6. Type Casting
7. Operators
8. Input and Output
9. Interview Questions
10. Practice Problems

---

# 1. Why Python?

Python is one of the most popular programming languages due to its simplicity, readability, and vast ecosystem. It is widely used in:

- Backend Development
- Artificial Intelligence
- Machine Learning
- Data Science
- Automation
- Cybersecurity
- Cloud Computing
- Agentic AI
- LLM Applications
- RAG Systems

## Why is Python popular in AI?

- Easy syntax
- Large community
- Extensive libraries
- Fast prototyping
- Rich ecosystem

Popular AI libraries include:

- NumPy
- Pandas
- FastAPI
- Pydantic
- LangChain
- LangGraph
- OpenAI SDK
- Transformers
- PyTorch
- TensorFlow

---

# 2. Installing Python

Download the latest version from:

https://python.org

Verify installation:

```bash
python --version
```

or

```bash
python3 --version
```

Check pip:

```bash
pip --version
```

---

# 3. Python Execution Flow

Python is an interpreted language.

Flow:

```
Python Code
      │
      ▼
Lexer
      │
      ▼
Parser
      │
      ▼
Bytecode (.pyc)
      │
      ▼
Python Virtual Machine
      │
      ▼
Output
```

### Interview Question

**Does Python compile code?**

Yes.

Python first compiles source code into **bytecode (.pyc)**.

The Python Virtual Machine (PVM) then executes the bytecode.

---

# 4. Variables

A variable stores a reference to an object.

Example:

```python
name = "Alice"
age = 25
salary = 85000.50
```

Python variables are dynamically typed.

```python
x = 10
print(type(x))

x = "Hello"
print(type(x))
```

Output

```
<class 'int'>
<class 'str'>
```

---

## Variable Naming Rules

✔ Can start with a letter or underscore

✔ Can contain numbers

✔ Case-sensitive

✔ Cannot use keywords

Correct:

```python
student_name = "John"
_marks = 90
employee2 = "Alice"
```

Incorrect:

```python
2student = "John"
class = 10
```

---

# Multiple Assignment

```python
a = b = c = 100
```

or

```python
x, y, z = 10, 20, 30
```

Swap variables

```python
a = 10
b = 20

a, b = b, a
```

No temporary variable needed.

---

# Memory Model

```python
a = 10
b = a
```

Both variables refer to the same object until one changes.

```
a ─────┐
       ▼
      10
       ▲
b ─────┘
```

---

# Mutable vs Immutable

Immutable objects:

- int
- float
- str
- tuple
- bool

Mutable objects:

- list
- dict
- set

Example

```python
x = "hello"

x += " world"
```

A new string object is created because strings are immutable.

---

# 5. Data Types

Python has several built-in data types.

## Numeric Types

```python
x = 10
y = 2.5
z = 4 + 3j
```

Types

```python
type(x)
type(y)
type(z)
```

Result

```
int
float
complex
```

---

## Boolean

```python
is_valid = True
```

---

## String

```python
name = "Python"
```

---

## List

Ordered

Mutable

Allows duplicates

```python
numbers = [1, 2, 3, 4]
```

Access

```python
numbers[0]
numbers[-1]
```

---

## Tuple

Ordered

Immutable

```python
coordinates = (10, 20)
```

---

## Set

Unordered

Unique values only

```python
languages = {"Python", "Java", "Go"}
```

---

## Dictionary

Key-value pairs

```python
student = {
    "name": "Alice",
    "age": 22,
    "marks": 91
}
```

Access

```python
student["name"]
```

---

# Summary Table

| Type | Ordered | Mutable | Duplicate Allowed |
|-------|----------|----------|-------------------|
| List | Yes | Yes | Yes |
| Tuple | Yes | No | Yes |
| Set | No | Yes | No |
| Dictionary | Yes (Python 3.7+) | Yes | Keys: No |

---

# 6. Type Casting

Implicit Casting

```python
x = 10
y = 5.5

print(x + y)
```

Output

```
15.5
```

Explicit Casting

```python
age = "25"

age = int(age)
```

Other examples

```python
float("5")

str(100)

list("Python")

tuple([1,2,3])

set([1,2,2,3])
```

---

# 7. Operators

## Arithmetic

```python
+
-
*
/
%
**
//
```

Example

```python
a = 15
b = 4

print(a+b)
print(a-b)
print(a*b)
print(a/b)
print(a//b)
print(a%b)
print(a**2)
```

---

## Comparison

```python
==
!=
>
<
>=
<=
```

---

## Logical

```python
and
or
not
```

---

## Assignment

```python
=
+=
-=
*=
/=
```

---

## Membership

```python
in

not in
```

Example

```python
"Py" in "Python"
```

---

## Identity

```python
is

is not
```

Example

```python
a = [1,2]
b = a
c = [1,2]

print(a is b)
print(a is c)
print(a == c)
```

Output

```
True
False
True
```

Interview Tip:

- `==` compares values.
- `is` compares object identity (memory reference).

---

# Operator Precedence

```
()

**

*, /, //, %

+, -

Comparison

not

and

or
```

---

# 8. Input and Output

Input

```python
name = input("Enter your name: ")
```

Integer Input

```python
age = int(input("Enter age: "))
```

Float Input

```python
salary = float(input())
```

Formatted Output

```python
name = "Alice"
age = 25

print(f"{name} is {age} years old.")
```

---

# 9. Most Asked Interview Questions

### Q1. Why is Python dynamically typed?

Python determines the type of an object at runtime. Variables reference objects rather than storing a fixed type.

---

### Q2. What is the difference between `is` and `==`?

- `==` compares values.
- `is` compares object identity.

---

### Q3. What are mutable objects?

Objects whose contents can be modified after creation.

Examples:

- list
- dict
- set

---

### Q4. What are immutable objects?

Objects that cannot be modified after creation.

Examples:

- int
- float
- tuple
- string

---

### Q5. What is type casting?

Converting one data type into another using functions like `int()`, `float()`, `str()`, and `list()`.

---

# 10. Practice Problems

### Easy

1. Swap two variables without using a third variable.

2. Convert a string to an integer.

3. Find the type of different variables.

4. Print the square of a number.

5. Check whether two variables reference the same object.

### Medium

1. Create a dictionary for a student and print all values.

2. Remove duplicate values from a list using a set.

3. Convert a list into a tuple.

4. Create a nested dictionary and access values.

5. Demonstrate the difference between `is` and `==`.

---

# Quick Revision

✅ Python is dynamically typed.

✅ Everything in Python is an object.

✅ Variables store references to objects.

✅ Lists, dictionaries, and sets are mutable.

✅ Strings and tuples are immutable.

✅ Use `==` for value comparison.

✅ Use `is` for identity comparison.

✅ Dictionaries preserve insertion order (Python 3.7+).

---
02_Control_Flow_and_Loops.md

---

# Part 4 – Interview Questions, Coding Problems & Cheat Sheet

## Most Asked Python Interview Questions

### Q1. Difference between `for` and `while` loops?

| for | while |
|------|--------|
| Used when iterations are known | Used when iterations are unknown |
| Iterates over iterable | Executes while condition is True |
| Cleaner syntax | More flexible |

Example

```python
for i in range(5):
    print(i)

i = 0
while i < 5:
    print(i)
    i += 1
```

---

### Q2. Difference between `break` and `continue`?

```python
for i in range(5):
    if i == 3:
        break
    print(i)
```

Output

```
0
1
2
```

---

```python
for i in range(5):
    if i == 3:
        continue
    print(i)
```

Output

```
0
1
2
4
```

---

### Q3. What does `pass` do?

`pass` is a placeholder.

```python
def future_function():
    pass
```

Useful while writing skeleton code.

---

### Q4. Can a `for` loop have an `else`?

Yes.

```python
for i in range(3):
    print(i)
else:
    print("Completed")
```

Output

```
0
1
2
Completed
```

The `else` executes only if the loop finishes normally (without `break`).

---

### Q5. Can a `while` loop have an `else`?

Yes.

```python
x = 0

while x < 3:
    print(x)
    x += 1
else:
    print("Done")
```

---

### Q6. Why is `range()` memory efficient?

`range()` generates values lazily instead of storing all numbers in memory.

```python
range(1000000000)
```

This does **not** create a list of one billion integers.

---

### Q7. Difference between `range()` and `list(range())`?

```python
range(5)
```

Creates a range object.

```python
list(range(5))
```

Creates a list in memory.

---

### Q8. What is `enumerate()`?

Adds an index while iterating.

```python
names = ["Alice", "Bob", "Charlie"]

for index, value in enumerate(names):
    print(index, value)
```

Output

```
0 Alice
1 Bob
2 Charlie
```

---

### Q9. What is `zip()`?

Combines multiple iterables.

```python
names = ["A","B","C"]
marks = [90,85,95]

for name, mark in zip(names, marks):
    print(name, mark)
```

Output

```
A 90
B 85
C 95
```

---

### Q10. What is Loop Optimization?

Avoid unnecessary work inside loops.

Bad

```python
for i in range(len(big_list)):
    print(len(big_list))
```

Better

```python
n = len(big_list)

for i in range(n):
    print(n)
```

---

### Q11. Which loop is faster?

Usually

```
for loop
```

because iteration over iterables is optimized in CPython.

---

### Q12. Infinite Loop?

```python
while True:
    print("Running")
```

Stop using

```python
break
```

---

### Q13. What is nested loop complexity?

```
for i:
    for j:
```

Time Complexity

```
O(n²)
```

---

### Q14. Complexity of iterating a list?

```
O(n)
```

---

### Q15. Complexity of nested three loops?

```
O(n³)
```

---

## Coding Problems

---

### Problem 1

Print numbers from 1 to 100.

```python
for i in range(1,101):
    print(i)
```

Complexity

```
Time O(n)

Space O(1)
```

---

### Problem 2

Print even numbers.

```python
for i in range(2,101,2):
    print(i)
```

---

### Problem 3

Sum of first N numbers.

```python
n = 10

total = 0

for i in range(1,n+1):
    total += i

print(total)
```

---

### Problem 4

Factorial

```python
n = 5

fact = 1

for i in range(1,n+1):
    fact *= i

print(fact)
```

---

### Problem 5

Reverse a string using loop

```python
text = "Python"

result = ""

for ch in text:
    result = ch + result

print(result)
```

---

### Problem 6

Count vowels

```python
word = "Programming"

count = 0

for ch in word.lower():
    if ch in "aeiou":
        count += 1

print(count)
```

---

### Problem 7

Largest number

```python
numbers = [10,5,17,22,3]

largest = numbers[0]

for num in numbers:
    if num > largest:
        largest = num

print(largest)
```

---

### Problem 8

Smallest number

```python
numbers=[5,8,1,3]

smallest=numbers[0]

for num in numbers:
    if num<smallest:
        smallest=num

print(smallest)
```

---

### Problem 9

Palindrome

```python
word="madam"

if word==word[::-1]:
    print("Palindrome")
```

---

### Problem 10

Prime Number

```python
n=29

prime=True

for i in range(2,n):
    if n%i==0:
        prime=False
        break

print(prime)
```

---

### Problem 11

Multiplication Table

```python
n=5

for i in range(1,11):
    print(f"{n} x {i} = {n*i}")
```

---

### Problem 12

Pattern

```
*
**
***
****
*****
```

```python
for i in range(1,6):
    print("*"*i)
```

---

### Problem 13

Reverse Triangle

```
*****
****
***
**
*
```

```python
for i in range(5,0,-1):
    print("*"*i)
```

---

### Problem 14

FizzBuzz

```python
for i in range(1,101):

    if i%15==0:
        print("FizzBuzz")

    elif i%3==0:
        print("Fizz")

    elif i%5==0:
        print("Buzz")

    else:
        print(i)
```

---

### Problem 15

Frequency Count

```python
text="banana"

freq={}

for ch in text:
    freq[ch]=freq.get(ch,0)+1

print(freq)
```

Output

```
{'b':1,'a':3,'n':2}
```

---

## Common Mistakes

### Forgetting Increment

```python
while True:
    print("Infinite")
```

---

### Modifying List During Iteration

Bad

```python
for item in numbers:
    numbers.remove(item)
```

Better

```python
for item in numbers[:]:
    numbers.remove(item)
```

---

### Wrong Indentation

```python
for i in range(5):
print(i)
```

Raises

```
IndentationError
```

---

### Using `== None`

Bad

```python
if value == None:
```

Better

```python
if value is None:
```

---

## Interview Tips

✔ Prefer `for` over `while` when possible.

✔ Use `enumerate()` instead of manual indexing.

✔ Use `zip()` for parallel iteration.

✔ Avoid unnecessary nested loops.

✔ Know the complexity of every loop.

✔ Use comprehensions for concise code, but avoid making them too complex.

✔ Understand `for-else` and `while-else`; they are Python-specific and occasionally appear in interviews.

---

# Quick Revision Cheat Sheet

| Concept | Syntax |
|----------|--------|
| if | `if condition:` |
| if-else | `if...else` |
| elif | `if...elif...else` |
| for | `for item in iterable:` |
| while | `while condition:` |
| break | Exit loop |
| continue | Skip current iteration |
| pass | Placeholder |
| range | `range(start, stop, step)` |
| enumerate | Index + value |
| zip | Iterate multiple iterables |
| List Comprehension | `[x for x in iterable]` |
| Dictionary Comprehension | `{k:v for ...}` |
| Set Comprehension | `{x for x in iterable}` |
| Generator Expression | `(x for x in iterable)` |

---

# Interview Summary

After completing this chapter, you should be able to:

- Write efficient `if`/`else` logic.
- Use `for` and `while` loops confidently.
- Explain `break`, `continue`, and `pass`.
- Use `range()`, `enumerate()`, and `zip()` effectively.
- Analyze loop time complexity.
- Solve common loop-based interview problems.
- Write Pythonic iteration code.
- Answer Python control flow questions in technical interviews.
  
