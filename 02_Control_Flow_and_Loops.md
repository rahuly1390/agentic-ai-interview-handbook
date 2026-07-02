# ⚡ Control Flow & Loops – Interview Cheat Sheet (Python)

> Ultra-quick revision for interviews (FAANG + AI Engineer roles)

---

# 1. if / elif / else

```python
if x > 0:
    pass
elif x == 0:
    pass
else:
    pass
```

✔ Used for decision making  
✔ Executes first matching condition only  

---

# 2. Nested if

```python
if x > 0:
    if x > 10:
        print("Big")
```

⚠ Avoid deep nesting (bad readability)

---

# 3. Ternary Operator

```python
result = "Yes" if x > 0 else "No"
```

✔ One-line condition

---

# 4. match-case (Python 3.10+)

```python
match value:
    case 1:
        print("One")
    case _:
        print("Default")
```

✔ Like switch-case  
✔ Used in structured branching

---

# 5. for loop

```python
for i in range(5):
    print(i)
```

✔ Used when iterations are known

---

# 6. while loop

```python
while condition:
    pass
```

✔ Used when condition-based looping needed

---

# 7. break / continue / pass

```python
break      # exit loop
continue   # skip iteration
pass       # placeholder
```

---

# 8. range()

```python
range(start, stop, step)
```

Example:
```python
range(1, 10, 2)
```

✔ Lazy evaluation (memory efficient)

---

# 9. enumerate()

```python
for i, val in enumerate(arr):
    print(i, val)
```

✔ Gives index + value

---

# 10. zip()

```python
for a, b in zip(list1, list2):
    print(a, b)
```

✔ Parallel iteration

---

# 11. Nested loops

```python
for i in range(n):
    for j in range(n):
        pass
```

⏱ Complexity: O(n²)

---

# 12. Loop Optimization

✔ Move invariant code outside loop  
✔ Avoid repeated function calls  
✔ Cache len()

```python
n = len(arr)
for i in range(n):
    pass
```

---

# 13. List Comprehension

```python
[x for x in range(10)]
```

✔ Faster + cleaner than loop

---

# 14. Dictionary Comprehension

```python
{k: v for k, v in zip(keys, values)}
```

---

# 15. Set Comprehension

```python
{x for x in arr}
```

✔ Removes duplicates

---

# 16. Generator Expression

```python
(x for x in range(10))
```

✔ Lazy evaluation  
✔ Memory efficient

---

# 17. Common Mistakes

❌ Modifying list while iterating  
❌ Infinite while loop  
❌ Using == None instead of is None  
❌ Deep nested loops  
❌ Ignoring break condition  

---

# 18. Complexity Cheat Sheet

| Pattern | Complexity |
|--------|------------|
| Single loop | O(n) |
| Nested loop | O(n²) |
| Triple loop | O(n³) |
| List comprehension | O(n) |
| range() | O(1) memory |

---

# 19. Most Asked Interview Questions

### Q1. Difference between for and while?
- for → known iteration
- while → condition-based

---

### Q2. break vs continue?
- break → exit loop
- continue → skip iteration

---

### Q3. Why enumerate?
Avoid manual indexing.

---

### Q4. Why zip?
Parallel iteration.

---

### Q5. Why comprehension?
Faster + Pythonic + readable.

---

# 20. Coding Patterns (VERY IMPORTANT)

### 1. Frequency count
```python
freq = {}
for x in arr:
    freq[x] = freq.get(x, 0) + 1
```

---

### 2. Two pointer (loop usage)
```python
l, r = 0, len(arr)-1
while l < r:
    l += 1
    r -= 1
```

---

### 3. Accumulator pattern
```python
total = 0
for x in arr:
    total += x
```

---

# 21. Agentic AI Connection

Control flow is used in:

- Agent loops
- Tool execution logic
- Retry mechanisms
- Multi-step reasoning (ReAct)
- Task planning workflows

Example:
```python
while not task_done:
    decide_action()
    execute_tool()
```

---

# 🚀 Final Revision Summary

✔ if/else = decision making  
✔ loops = iteration engine  
✔ comprehensions = fast transformations  
✔ break/continue = control flow tuning  
✔ zip/enumerate = clean iteration  
✔ generator = memory optimization  
