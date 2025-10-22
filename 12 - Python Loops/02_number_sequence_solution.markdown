# Solution to Python Class Exercise: Number Sequence Printer

This document provides the solution to the Python class exercise from the Python Loops tutorial, where the task is to create a program that uses `while` and `for` loops to print number sequences with specific conditions. Below is the solution code, followed by a detailed explanation tailored for beginners.

---

## Solution Code

```python
# number_sequence.py
# This program prints number sequences using while and for loops with specific conditions

"""
Program: Number Sequence Printer
Author: [Your Name]
Purpose: Demonstrates using while and for loops to print number sequences with break, continue, and else
"""

# While loop to print 1 to 5
print("While Loop (1 to 5):")
i = 1
while i <= 5:
    print(i)  # Outputs: 1, 2, 3, 4, 5
    i += 1

# While loop with break to print 1 to 7, stop at 4
print("While Loop with Break (stop at 4):")
i = 1
while i <= 7:
    print(i)  # Outputs: 1, 2, 3, 4
    if i == 4:
        break
    i += 1

# While loop with continue to print odd numbers 1 to 9
print("While Loop with Continue (odd numbers 1 to 9):")
i = 0
while i < 9:
    i += 1
    if i % 2 == 0:  # Skip even numbers
        continue
    print(i)  # Outputs: 1, 3, 5, 7, 9

# For loop with range(1, 6) to print 1 to 5
print("For Loop (range 1 to 5):")
for x in range(1, 6):
    print(x)  # Outputs: 1, 2, 3, 4, 5

# For loop with range(2, 10, 2) to print even numbers
print("For Loop (even numbers 2 to 8):")
for x in range(2, 10, 2):
    print(x)  # Outputs: 2, 4, 6, 8

# For loop with range(1, 4) and else
print("For Loop with Else (1 to 3):")
for x in range(1, 4):
    print(x)  # Outputs: 1, 2, 3
else:
    print("Done")  # Outputs: Done
```

**Expected Output**:
```
While Loop (1 to 5):
1
2
3
4
5
While Loop with Break (stop at 4):
1
2
3
4
While Loop with Continue (odd numbers 1 to 9):
1
3
5
7
9
For Loop (range 1 to 5):
1
2
3
4
5
For Loop (even numbers 2 to 8):
2
4
6
8
For Loop with Else (1 to 3):
1
2
3
Done
```

---

## Explanation

### Objective
The exercise requires creating a Python program (`number_sequence.py`) that:
- Uses a `while` loop to print numbers from 1 to 5.
- Uses a `while` loop with `break` to print numbers from 1 to 7, stopping at 4.
- Uses a `while` loop with `continue` to print odd numbers from 1 to 9.
- Uses a `for` loop with `range(1, 6)` to print numbers.
- Uses a `for` loop with `range(2, 10, 2)` to print even numbers.
- Uses a `for` loop with `range(1, 4)` and `else` to print `"Done"` after.
- Includes comments to explain each step.
- Runs correctly with `python number_sequence.py`.

### Line-by-Line Breakdown
Let’s walk through the code to understand each part, its input, output, and purpose:

1. **File Creation**:
   - The code is saved in a file named `number_sequence.py`. This ensures Python recognizes it as a Python script when you run `python number_sequence.py`.

2. **Single-Line Comment**:
   ```python
   # number_sequence.py
   # This program prints number sequences using while and for loops with specific conditions
   ```
   - **Purpose**: Describes the file and program purpose. Ignored by Python.
   - **Input**: None.
   - **Output**: None.
   - **Side Effects**: None.

3. **Multiline Comment**:
   ```python
   """
   Program: Number Sequence Printer
   Author: [Your Name]
   Purpose: Demonstrates using while and for loops to print number sequences with break, continue, and else
   """
   ```
   - **Purpose**: Provides detailed documentation. Ignored by Python since it’s not assigned.
   - **Input**: None.
   - **Output**: None.
   - **Side Effects**: None.

4. **While Loop (1 to 5)**:
   ```python
   print("While Loop (1 to 5):")
   i = 1
   while i <= 5:
       print(i)  # Outputs: 1, 2, 3, 4, 5
       i += 1
   ```
   - **Purpose**: Prints numbers from 1 to 5 using a `while` loop.
   - **Line-by-Line**:
     - `print("While Loop (1 to 5):")`: Prints header. **Output**: `While Loop (1 to 5):`.
     - `i = 1`: Initializes `i`. **Side Effects**: `i` is set.
     - `while i <= 5`: Runs while `i <= 5`. **Input**: `i`.
     - `print(i)`: Prints `i`. **Output**: `1`, `2`, `3`, `4`, `5`.
     - `i += 1`: Increments `i`. **Side Effects**: Updates `i`.

5. **While Loop with Break (Stop at 4)**:
   ```python
   print("While Loop with Break (stop at 4):")
   i = 1
   while i <= 7:
       print(i)  # Outputs: 1, 2, 3, 4
       if i == 4:
           break
       i += 1
   ```
   - **Purpose**: Prints numbers from 1 to 7, stopping at 4.
   - **Line-by-Line**:
     - `print("While Loop with Break (stop at 4):")`: Prints header.
     - `i = 1`: Initializes `i`.
     - `while i <= 7`: Runs while `i <= 7`.
     - `print(i)`: Prints `i`. **Output**: `1`, `2`, `3`, `4`.
     - `if i == 4: break`: Exits loop when `i` is 4.
     - `i += 1`: Increments `i` (skipped after `break`).

6. **While Loop with Continue (Odd Numbers 1 to 9)**:
   ```python
   print("While Loop with Continue (odd numbers 1 to 9):")
   i = 0
   while i < 9:
       i += 1
       if i % 2 == 0:  # Skip even numbers
           continue
       print(i)  # Outputs: 1, 3, 5, 7, 9
   ```
   - **Purpose**: Prints odd numbers from 1 to 9.
   - **Line-by-Line**:
     - `print("While Loop with Continue (odd numbers 1 to 9):")`: Prints header.
     - `i = 0`: Initializes `i`.
     - `while i < 9`: Runs while `i < 9`.
     - `i += 1`: Increments `i` first to avoid infinite loop.
     - `if i % 2 == 0: continue`: Skips even numbers.
     - `print(i)`: Prints odd `i`. **Output**: `1`, `3`, `5`, `7`, `9`.

7. **For Loop with range(1, 6)**:
   ```python
   print("For Loop (range 1 to 5):")
   for x in range(1, 6):
       print(x)  # Outputs: 1, 2, 3, 4, 5
   ```
   - **Purpose**: Prints numbers from 1 to 5 using `range(1, 6)`.
   - **Line-by-Line**:
     - `print("For Loop (range 1 to 5):")`: Prints header.
     - `for x in range(1, 6)`: Iterates from 1 to 5.
     - `print(x)`: Prints `x`. **Output**: `1`, `2`, `3`, `4`, `5`.

8. **For Loop with range(2, 10, 2)**:
   ```python
   print("For Loop (even numbers 2 to 8):")
   for x in range(2, 10, 2):
       print(x)  # Outputs: 2, 4, 6, 8
   ```
   - **Purpose**: Prints even numbers from 2 to 8.
   - **Line-by-Line**:
     - `print("For Loop (even numbers 2 to 8):")`: Prints header.
     - `for x in range(2, 10, 2)`: Iterates from 2 to 8, step 2.
     - `print(x)`: Prints `x`. **Output**: `2`, `4`, `6`, `8`.

9. **For Loop with Else (1 to 3)**:
   ```python
   print("For Loop with Else (1 to 3):")
   for x in range(1, 4):
       print(x)  # Outputs: 1, 2, 3
   else:
       print("Done")  # Outputs: Done
   ```
   - **Purpose**: Prints numbers from 1 to 3, then `"Done"`.
   - **Line-by-Line**:
     - `print("For Loop with Else (1 to 3):")`: Prints header.
     - `for x in range(1, 4)`: Iterates from 1 to 3.
     - `print(x)`: Prints `x`. **Output**: `1`, `2`, `3`.
     - `else: print("Done")`: Runs after loop. **Output**: `Done`.

### Visual Description
When you run `python number_sequence.py` in the terminal, the output is:
```
While Loop (1 to 5):
1
2
3
4
5
While Loop with Break (stop at 4):
1
2
3
4
While Loop with Continue (odd numbers 1 to 9):
1
3
5
7
9
For Loop (range 1 to 5):
1
2
3
4
5
For Loop (even numbers 2 to 8):
2
4
6
8
For Loop with Else (1 to 3):
1
2
3
Done
```
Each section is clearly labeled, with numbers printed one per line, and the `else` block confirming completion.

### Common Mistakes and Fixes
1. **Forgetting to Increment in `while` Loop**:
   - **Mistake**:
     ```python
     i = 1
     while i <= 5:
         print(i)  # Infinite loop
     ```
   - **Error**: Infinite loop.
   - **Fix**: Add `i += 1`:
     ```python
     i = 1
     while i <= 5:
         print(i)
         i += 1
     ```
2. **Incrementing After `continue`**:
   - **Mistake**:
     ```python
     i = 0
     while i < 9:
         if i % 2 == 0:
             continue
         print(i)  # Infinite loop
         i += 1
     ```
   - **Error**: Infinite loop if `i` is even.
   - **Fix**: Increment before `continue`:
     ```python
     i = 0
     while i < 9:
         i += 1
         if i % 2 == 0:
             continue
         print(i)
     ```
3. **Misunderstanding `range`**:
   - **Mistake**:
     ```python
     for x in range(6):  # Expecting 0 to 6
         print(x)
     ```
   - **Error**: Outputs `0` to `5`.
   - **Fix**: Use `range(7)` for `0` to `6`.
4. **Empty Loop Without `pass`**:
   - **Mistake**:
     ```python
     for x in range(3):  # SyntaxError
     ```
   - **Error**: `SyntaxError`.
   - **Fix**: Use `pass`:
     ```python
     for x in range(3):
         pass
     ```
5. **Wrong File Extension**:
   - **Mistake**: Saving as `number_sequence.txt`.
   - **Fix**: Save as `number_sequence.py` and run with `python number_sequence.py`.

### Validation Check
To confirm the program works:
1. Save the code in `number_sequence.py`.
2. Open a terminal, navigate to the file’s directory, and run `python number_sequence.py`.
3. Verify the output matches: `1` to `5`, `1` to `4` with break, odd numbers `1` to `9`, `1` to `5`, `2` to `8`, and `1` to `3` with `Done`.
4. Test with different ranges (e.g., `range(1, 7)` for `1` to `6`) to ensure flexibility.
5. Add `print(type(x))` in a `for` loop to confirm `x` is an integer (`<class 'int'>`).

### One-Line Takeaway
This program demonstrates `while` and `for` loops with `break`, `continue`, and `else` to print number sequences, using `range()` and modulo for specific patterns.