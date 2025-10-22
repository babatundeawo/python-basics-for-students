# Python Loops for Beginners

This tutorial covers Python's `while` and `for` loops, including `break`, `continue`, `else`, `range()`, nested loops, and the `pass` statement. Below is a beginner-friendly teaching package based on the provided lesson note, designed to guide learners toward intermediate-level mastery with practical examples and exercises.

---

## Section 1 — Topical Explanations

### Learning Goals
- Understand how to use `while` loops to execute code while a condition is true.
- Learn `for` loops to iterate over sequences (lists, tuples, dictionaries, sets, strings).
- Use `break` to exit loops, `continue` to skip iterations, and `else` for loop completion.
- Apply `range()` to generate number sequences for `for` loops.
- Explore nested loops and the `pass` statement.
- Emphasize the importance of loop variable updates to avoid infinite loops.

### The while Loop
A `while` loop executes a block of code as long as a condition is `True`. It requires an index variable and an update to avoid infinite loops.

**Example Code**:
```python
# Print i as long as i is less than 6
i = 1
while i < 6:
    print(i)  # Outputs: 1, 2, 3, 4, 5 (one per line)
    i += 1
```
- **Line-by-Line Explanation**:
  - `i = 1`: Initializes `i`. **Input**: `1`. **Output**: None. **Side Effects**: `i` is set.
  - `while i < 6:`: Checks if `i < 6`. **Input**: `i`. **Output**: None.
  - `print(i)`: Prints current `i`. **Output**: `1`, `2`, ..., `5`.
  - `i += 1`: Increments `i`. **Side Effects**: Updates `i` to prevent infinite loop.
- **Visual Description**: Terminal shows numbers `1` to `5`, each on a new line.
- **Common Mistake**: Forgetting to increment `i`, causing an infinite loop.
  - **Error**: Program runs indefinitely.
  - **Fix**: Always update the loop variable, e.g., `i += 1`.
- **Validation Check**: Verify output stops at `5` (not `6`) since `i < 6`.

### The break Statement (while)
The `break` statement exits a `while` loop immediately, even if the condition is `True`.

**Example Code**:
```python
i = 1
while i < 6:
    print(i)  # Outputs: 1, 2, 3
    if i == 3:
        break
    i += 1
```
- **Explanation**:
  - `if i == 3: break`: Exits when `i` is `3`. **Output**: `1`, `2`, `3`.
- **Common Mistake**: Placing `break` after `i += 1`, printing `4`.
  - **Fix**: Place `break` before increment if stopping at `3`.

### The continue Statement (while)
The `continue` statement skips the current iteration and proceeds to the next.

**Example Code**:
```python
i = 0
while i < 6:
    i += 1
    if i == 3:
        continue
    print(i)  # Outputs: 1, 2, 4, 5, 6
```
- **Explanation**:
  - `i += 1`: Increments first to avoid infinite loop.
  - `if i == 3: continue`: Skips printing when `i` is `3`. **Output**: Skips `3`.
- **Common Mistake**: Incrementing after `continue`, causing an infinite loop.
  - **Error**: `i` never increases if `continue` is hit.
  - **Fix**: Increment before `continue`.

### The else Statement (while)
The `else` block runs when the `while` condition becomes `False`, unless stopped by `break`.

**Example Code**:
```python
i = 1
while i < 6:
    print(i)  # Outputs: 1, 2, 3, 4, 5
    i += 1
else:
    print("i is no longer less than 6")  # Outputs: i is no longer less than 6
```
- **Explanation**: `else` executes when `i < 6` is `False` (`i = 6`). **Output**: Message after loop.
- **Common Mistake**: Expecting `else` to run after `break`.
  - **Fix**: `else` only runs if loop completes naturally.

### The for Loop
A `for` loop iterates over a sequence (list, tuple, dictionary, set, string) without needing an index variable.

**Example Code**:
```python
fruits = ["apple", "banana", "cherry"]
for x in fruits:
    print(x)  # Outputs: apple, banana, cherry (one per line)
```
- **Explanation**:
  - `for x in fruits`: Iterates over each item in `fruits`. **Output**: Each fruit name.
- **Visual Description**: Terminal shows one fruit per line.
- **Common Mistake**: Modifying the sequence during iteration, e.g., `fruits.append("orange")`.
  - **Error**: May cause unexpected behavior or infinite loop.
  - **Fix**: Modify a copy or use a different approach.

### Looping Through a String
Strings are iterable, allowing `for` loops to process each character.

**Example Code**:
```python
for x in "banana":
    print(x)  # Outputs: b, a, n, a, n, a (one per line)
```
- **Explanation**: Iterates over each character. **Output**: Each letter on a new line.

### The break Statement (for)
The `break` statement exits a `for` loop early.

**Example Code**:
```python
fruits = ["apple", "banana", "cherry"]
for x in fruits:
    print(x)  # Outputs: apple, banana
    if x == "banana":
        break
```
- **Explanation**: Exits after printing `banana`. **Output**: `apple`, `banana`.
- **Variation**: If `break` is before `print`:
  ```python
  for x in fruits:
      if x == "banana":
          break
      print(x)  # Outputs: apple
  ```

### The continue Statement (for)
The `continue` statement skips the current iteration in a `for` loop.

**Example Code**:
```python
fruits = ["apple", "banana", "cherry"]
for x in fruits:
    if x == "banana":
        continue
    print(x)  # Outputs: apple, cherry
```
- **Explanation**: Skips printing `banana`. **Output**: `apple`, `cherry`.

### The range() Function
The `range(start, stop, step)` function generates a sequence of numbers for `for` loops. It excludes `stop`.

**Example Code**:
```python
for x in range(6):
    print(x)  # Outputs: 0, 1, 2, 3, 4, 5
for x in range(2, 6):
    print(x)  # Outputs: 2, 3, 4, 5
for x in range(2, 30, 3):
    print(x)  # Outputs: 2, 5, 8, ..., 29
```
- **Explanation**:
  - `range(6)`: Generates `0` to `5`.
  - `range(2, 6)`: Generates `2` to `5`.
  - `range(2, 30, 3)`: Generates `2`, `5`, ..., `29` (step of `3`).
- **Common Mistake**: Expecting `range(6)` to include `6`.
  - **Fix**: `range(stop)` goes up to `stop-1`.

### Else in for Loop
The `else` block in a `for` loop runs when the loop completes, unless stopped by `break`.

**Example Code**:
```python
for x in range(6):
    print(x)  # Outputs: 0, 1, 2, 3, 4, 5
else:
    print("Finally finished!")  # Outputs: Finally finished!
```
- **Example with break**:
  ```python
  for x in range(6):
      if x == 3: break
      print(x)  # Outputs: 0, 1, 2
  else:
      print("Finally finished!")  # Not executed
  ```
- **Explanation**: `else` skips if `break` is used.

### Nested Loops
A loop inside a loop executes the inner loop for each iteration of the outer loop.

**Example Code**:
```python
adj = ["red", "big", "tasty"]
fruits = ["apple", "banana", "cherry"]
for x in adj:
    for y in fruits:
        print(x, y)  # Outputs: red apple, red banana, ..., tasty cherry
```
- **Explanation**: Inner loop runs for each outer loop iteration. **Output**: All combinations (9 pairs).
- **Common Mistake**: Incorrect indentation of inner loop.
  - **Fix**: Indent inner loop 4 spaces more than outer loop.

### The pass Statement
The `pass` statement is a placeholder for empty loops to avoid errors.

**Example Code**:
```python
for x in [0, 1, 2]:
    pass  # No error, no output
```
- **Explanation**: Prevents `SyntaxError` for empty loop.
- **Common Mistake**: Empty loop without `pass`.
  - **Error**: `SyntaxError`.
  - **Fix**: Use `pass`.

**One-Line Takeaway**: Python’s `while` and `for` loops, with `break`, `continue`, `else`, `range()`, and nested loops, provide flexible iteration over sequences and conditions.

---

## Section 2 — Class Exercise

### Exercise: Number Sequence Printer

**Objective**: Write a Python program that uses `while` and `for` loops to print number sequences with specific conditions.

**Step-by-Step Instructions**:
1. Create a file named `number_sequence.py`.
2. Perform and print:
   - Use a `while` loop to print numbers from 1 to 5.
   - Use a `while` loop with `break` to print numbers from 1 to 7, stopping at 4.
   - Use a `while` loop with `continue` to print odd numbers from 1 to 9.
   - Use a `for` loop with `range(1, 6)` to print numbers.
   - Use a `for` loop with `range(2, 10, 2)` to print even numbers.
   - Use a `for` loop with `range(1, 4)` and `else` to print `"Done"` after.
3. Add comments to explain each step.
4. Run with `python number_sequence.py`.

**Hints**:
- Ensure `while` loops increment to avoid infinite loops.
- Use `if` with modulo (`%`) to detect odd/even numbers.
- Place `continue` after increment in `while` loops.

**Checkpoint**:
- Verify output matches expected sequences.
- Ensure `else` block runs only without `break`.

**Example Output**:
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

## Section 3 — Weekly Project

### Project: Shopping List Processor

**Objective**: Create a Python program that processes a shopping list using loops to manage items and quantities.

**Milestones**:
1. Create a file named `shopping_list.py`.
2. Declare a list `items = ["milk", "bread", "eggs", "butter"]` and quantities `quantities = [2, 1, 12, 3]`.
3. Perform:
   - Use a `for` loop to print each item and its quantity (e.g., `"milk: 2"`).
   - Use a `while` loop to print items with quantities > 1, stopping if an item is `"eggs"`.
   - Use a `for` loop with `continue` to print items except `"bread"`.
   - Use a nested `for` loop to pair each item with a status list `["needed", "bought"]`.
   - Use a `for` loop with `range(1, 4)` and `else` to print first three items and `"List processed"`.
   - Validate quantities are positive with a `for` loop; print `"Invalid quantity"` for any negative.
4. Print results with f-strings and comments.
5. Run with `python shopping_list.py`.

**Deliverables**:
- A working `shopping_list.py` file.
- Output showing item processing and validations.

**Research Prompts**:
- How do `while` and `for` loops differ in handling dynamic versus fixed sequences?
- Why is avoiding infinite loops critical, and how can it be ensured?

**Assessment Criteria**:
- Code runs without errors.
- Loops (`while`, `for`, nested) produce correct outputs.
- Validation checks work.
- Output is clear and commented.
- `break`, `continue`, and `else` are used correctly.

**Extension Idea**:
- Add a `while` loop to simulate reducing quantities by 1 until 0 for one item.
- Use a `for` loop to create a dictionary mapping items to quantities.

**Example Output** (for given `items` and `quantities`):
```
Shopping List:
milk: 2
bread: 1
eggs: 12
butter: 3
Items with Quantity > 1:
milk: 2
Skip bread:
milk: 2
eggs: 12
butter: 3
Item Status Pairs:
milk needed
milk bought
bread needed
bread bought
eggs needed
eggs bought
butter needed
butter bought
First Three Items:
milk
bread
eggs
List processed
All quantities are valid
```

---

## Completion Checklist
- [ ] Understood `while` loops with condition-based iteration.
- [ ] Used `for` loops to iterate over sequences and `range()`.
- [ ] Applied `break`, `continue`, and `else` in loops.
- [ ] Implemented nested loops and `pass` statement.
- [ ] Avoided infinite loops by updating loop variables.
- [ ] Completed the class exercise and verified the output.
- [ ] Started the weekly project and planned the shopping list processor.
- [ ] Fixed at least one common mistake (e.g., missing increment in `while`).