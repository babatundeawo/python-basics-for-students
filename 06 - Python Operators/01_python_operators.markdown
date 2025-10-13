# Python Operators for Beginners

This tutorial covers Python operators, including arithmetic, assignment, comparison, logical, identity, membership, and bitwise operators, as well as operator precedence. Below is a beginner-friendly teaching package based on the provided lesson note, designed to guide learners toward intermediate-level mastery with practical examples and exercises.

---

## Section 1 — Topical Explanations

### Learning Goals
- Understand the purpose and use of Python’s operator groups: arithmetic, assignment, comparison, logical, identity, membership, and bitwise.
- Learn how to apply operators in expressions with numbers, strings, and lists.
- Master operator precedence to control the order of operations.
- Explore practical applications of operators in real-world scenarios.
- Validate operator usage with type checks and error handling.

### Arithmetic Operators
Arithmetic operators perform mathematical operations on numeric values.

**Example Code**:
```python
x = 10
y = 3
print(x + y)   # Addition: Outputs 13
print(x - y)   # Subtraction: Outputs 7
print(x * y)   # Multiplication: Outputs 30
print(x / y)   # Division: Outputs 3.333...
print(x % y)   # Modulus: Outputs 1
print(x ** y)  # Exponentiation: Outputs 1000
print(x // y)  # Floor division: Outputs 3
```
- **Line-by-Line Explanation**:
  - `x = 10`, `y = 3`: Assigns integers to variables. **Input**: `10`, `3`. **Output**: None. **Side Effects**: `x` holds `10`, `y` holds `3`.
  - `x + y`: Adds `10 + 3`. **Output**: `13`.
  - `x - y`: Subtracts `3` from `10`. **Output**: `7`.
  - `x * y`: Multiplies `10 * 3`. **Output**: `30`.
  - `x / y`: Divides `10 / 3`. **Output**: `3.333...` (float).
  - `x % y`: Remainder of `10 / 3`. **Output**: `1`.
  - `x ** y`: `10` raised to power `3`. **Output**: `1000`.
  - `x // y`: Floor division, rounds down `10 / 3`. **Output**: `3`.
- **Visual Description**: Terminal shows numeric results on separate lines.
- **Common Mistake**: Dividing by zero, e.g., `x / 0`.
  - **Error**: `ZeroDivisionError`.
  - **Fix**: Ensure the denominator is non-zero.
- **Validation Check**: Verify types with `print(type(x / y))` (should be `<class 'float'>` for division).

### Assignment Operators
Assignment operators assign values to variables, often combining with arithmetic operations.

**Example Code**:
```python
x = 5  # Assign 5 to x
x += 3  # Add 3 to x (x = x + 3)
print(x)  # Outputs: 8
x *= 2  # Multiply x by 2 (x = x * 2)
print(x)  # Outputs: 16
```
- **Explanation**:
  - `x = 5`: Assigns `5`. **Output**: None. **Side Effects**: `x` holds `5`.
  - `x += 3`: Equivalent to `x = x + 3`. **Output**: None. **Side Effects**: `x` becomes `8`.
  - `x *= 2`: Equivalent to `x = x * 2`. **Output**: None. **Side Effects**: `x` becomes `16`.
- **Common Mistake**: Using `=` instead of `==` in comparisons.
  - **Error**: Assigns instead of compares.
  - **Fix**: Use `==` for equality checks.

### Comparison Operators
Comparison operators compare two values, returning `True` or `False`.

**Example Code**:
```python
x = 10
y = 5
print(x == y)  # Equal: Outputs False
print(x != y)  # Not equal: Outputs True
print(x > y)   # Greater than: Outputs True
print(x <= y)  # Less than or equal: Outputs False
```
- **Explanation**:
  - `x == y`: Checks if `10` equals `5`. **Output**: `False`.
  - `x != y`: Checks if `10` is not `5`. **Output**: `True`.
  - `x > y`: Checks if `10` is greater than `5`. **Output**: `True`.
  - `x <= y`: Checks if `10` is less than or equal to `5`. **Output**: `False`.
- **Common Mistake**: Using `=` instead of `==`.
  - **Error**: Assigns instead of compares.
  - **Fix**: Use `==` for equality.

### Logical Operators
Logical operators combine boolean expressions.

**Example Code**:
```python
x = 7
print(x < 10 and x > 5)  # Outputs: True
print(x < 5 or x < 10)   # Outputs: True
print(not (x < 10))      # Outputs: False
```
- **Explanation**:
  - `and`: True if both conditions are true (`7 < 10` and `7 > 5`). **Output**: `True`.
  - `or`: True if at least one condition is true (`7 < 5` or `7 < 10`). **Output**: `True`.
  - `not`: Reverses the result (`not (7 < 10)`). **Output**: `False`.
- **Common Mistake**: Using `&` instead of `and`.
  - **Fix**: Use `and` for logical operations, `&` for bitwise.

### Identity Operators
Identity operators (`is`, `is not`) check if two variables refer to the same object in memory.

**Example Code**:
```python
x = [1, 2]
y = [1, 2]
z = x
print(x is y)      # Outputs: False
print(x is z)      # Outputs: True
print(x is not y)  # Outputs: True
```
- **Explanation**:
  - `x is y`: False because `x` and `y` are different objects, even with the same values.
  - `x is z`: True because `z` references the same object as `x`.
- **Common Mistake**: Using `is` instead of `==` for value comparison.
  - **Fix**: Use `==` for values, `is` for identity.

### Membership Operators
Membership operators (`in`, `not in`) test if a value is in a sequence.

**Example Code**:
```python
text = "Hello, World!"
print("World" in text)      # Outputs: True
print("Python" not in text) # Outputs: True
```
- **Explanation**:
  - `"World" in text`: True because `"World"` is a substring of `text`.
  - `"Python" not in text`: True because `"Python"` is not in `text`.
- **Common Mistake**: Using `in` with non-sequences, e.g., `5 in 123`.
  - **Error**: `TypeError`.
  - **Fix**: Use sequences like strings or lists.

### Bitwise Operators
Bitwise operators work on binary representations of numbers.

**Example Code**:
```python
x = 5  # Binary: 0101
y = 3  # Binary: 0011
print(x & y)  # AND: Outputs 1 (0001)
print(x | y)  # OR: Outputs 7 (0111)
print(x ^ y)  # XOR: Outputs 6 (0110)
```
- **Explanation**:
  - `&`: Sets bits to `1` if both are `1` (`0101 & 0011 = 0001`).
  - `|`: Sets bits to `1` if either is `1` (`0101 | 0011 = 0111`).
  - `^`: Sets bits to `1` if only one is `1` (`0101 ^ 0011 = 0110`).
- **Common Mistake**: Confusing `&` with `and`.
  - **Fix**: Use `&` for bitwise, `and` for logical.

### Operator Precedence
Operator precedence determines the order of operations. Parentheses have the highest precedence.

**Example Code**:
```python
print((6 + 3) - (6 + 3))  # Outputs: 0
print(100 + 5 * 3)        # Outputs: 115
print(5 + 4 - 7 + 3)      # Outputs: 5
```
- **Explanation**:
  - `(6 + 3) - (6 + 3)`: Parentheses first, `9 - 9`. **Output**: `0`.
  - `100 + 5 * 3`: Multiplication (`5 * 3 = 15`) before addition (`100 + 15`). **Output**: `115`.
  - `5 + 4 - 7 + 3`: Left-to-right for same precedence. **Output**: `5`.
- **Common Mistake**: Ignoring precedence, expecting `100 + 5 * 3` to be `315`.
  - **Fix**: Use parentheses, e.g., `(100 + 5) * 3` for `315`.

**One-Line Takeaway**: Python operators enable arithmetic, assignment, comparison, logical, identity, membership, and bitwise operations, with precedence controlling evaluation order.

---

## Section 2 — Class Exercise

### Exercise: Operator Explorer

**Objective**: Write a Python program that demonstrates arithmetic, comparison, logical, and membership operators.

**Step-by-Step Instructions**:
1. Create a file named `operators.py`.
2. Declare variables:
   - `a` (integer, e.g., `15`).
   - `b` (integer, e.g., `4`).
   - `text` (string, e.g., `"Python Programming"`).
3. Perform and print:
   - Arithmetic: `a + b`, `a // b`, `a % b`.
   - Comparison: `a > b`, `a == b * 4`.
   - Logical: `a > 10 and b < 5`.
   - Membership: `"Python" in text`.
4. Add comments to explain each operation.
5. Run the program with `python operators.py`.

**Hints**:
- Use `print()` with descriptive labels, e.g., `print("Sum:", a + b)`.
- Check precedence for expressions like `a == b * 4`.

**Checkpoint**:
- Verify output matches expected results.
- Confirm logical and membership operators return `True` or `False`.

**Example Output** (for `a = 15`, `b = 4`, `text = "Python Programming"`):
```
Sum: 19
Floor Division: 3
Modulus: 3
Is a > b? True
Is a equal to b * 4? False
Is a > 10 and b < 5? True
Is 'Python' in text? True
```

---

## Section 3 — Weekly Project

### Project: Budget Calculator

**Objective**: Create a Python program that uses operators to manage a simple budget, incorporating arithmetic, comparison, logical, and membership operators.

**Milestones**:
1. Create a file named `budget_calculator.py`.
2. Declare variables:
   - `income` (float, e.g., `5000.0`).
   - `rent` (float, e.g., `1500.0`).
   - `groceries` (float, e.g., `300.0`).
   - `categories` (list, e.g., `["rent", "groceries", "savings"]`).
3. Calculate:
   - Total expenses (`rent + groceries`).
   - Savings (`income - total expenses`).
   - Budget status (logical check: `savings > 0 and savings >= income * 0.2`).
   - Whether `"savings"` is in `categories`.
4. Print results with f-strings, including type validation for `income`.
5. Add comments to explain each step.

**Deliverables**:
- A working `budget_calculator.py` file.
- Output showing calculations, status, and validations.

**Research Prompts**:
- Why does `is` differ from `==` in Python?
- How does floor division (`//`) differ from regular division (`/`)?

**Assessment Criteria**:
- Code runs without errors.
- Calculations are accurate.
- Logical and membership checks return correct booleans.
- Output is formatted clearly.
- Comments explain steps.

**Extension Idea**:
- Add a boolean `is_high_savings` (check if `savings` is at least 30% of `income`).
- Calculate percentage of `income` spent on `rent`.

**Example Output** (for `income = 5000.0`, `rent = 1500.0`, `groceries = 300.0`, `categories = ["rent", "groceries", "savings"]`):
```
Budget Summary:
Total Expenses: 1800.0
Savings: 3200.0
Is budget healthy? True
Is 'savings' in categories? True
Is income a float? True
```

---

## Completion Checklist
- [ ] Understood arithmetic, assignment, comparison, logical, identity, membership, and bitwise operators.
- [ ] Applied operators in expressions with correct precedence.
- [ ] Used `isinstance()` for type validation.
- [ ] Completed the class exercise and verified the output.
- [ ] Started the weekly project and planned the budget calculator.
- [ ] Fixed at least one common mistake (e.g., division by zero or using `=` instead of `==`).