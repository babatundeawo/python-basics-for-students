# Solution to Python Weekly Project: Budget Calculator

This document provides the solution to the Python weekly project from the Python Operators tutorial, where the task is to create a program that uses operators to manage a simple budget, incorporating arithmetic, comparison, logical, and membership operators. Below is the solution code, followed by a detailed explanation tailored for beginners.

---

## Solution Code

```python
# budget_calculator.py
# This program manages a simple budget using operators

"""
Program: Budget Calculator
Author: [Your Name]
Purpose: Uses arithmetic, comparison, logical, and membership operators to manage a budget
"""

# Declare variables
income = 5000.0  # Float for monthly income
rent = 1500.0    # Float for rent expense
groceries = 300.0  # Float for groceries expense
categories = ["rent", "groceries", "savings"]  # List of expense categories

# Calculate budget metrics
total_expenses = rent + groceries  # Sum of expenses
savings = income - total_expenses   # Remaining savings
is_healthy_budget = savings > 0 and savings >= income * 0.2  # Logical check for healthy budget

# Print budget summary using f-strings
print("Budget Summary:")
print(f"Total Expenses: {total_expenses}")
print(f"Savings: {savings}")
print(f"Is budget healthy? {is_healthy_budget}")
print(f"Is 'savings' in categories? {'savings' in categories}")
print(f"Is income a float? {isinstance(income, float)}")
```

**Expected Output** (for `income = 5000.0`, `rent = 1500.0`, `groceries = 300.0`, `categories = ["rent", "groceries", "savings"]`):
```
Budget Summary:
Total Expenses: 1800.0
Savings: 3200.0
Is budget healthy? True
Is 'savings' in categories? True
Is income a float? True
```

---

## Explanation

### Objective
The project requires creating a Python program (`budget_calculator.py`) that:
- Declares variables: `income` (float), `rent` (float), `groceries` (float), and `categories` (list).
- Calculates:
  - Total expenses (`rent + groceries`).
  - Savings (`income - total expenses`).
  - Budget status (logical check: `savings > 0 and savings >= income * 0.2`).
  - Whether `"savings"` is in `categories`.
- Prints results using f-strings, including type validation for `income`.
- Includes comments to explain each step.
- Runs correctly with `python budget_calculator.py`.

### Line-by-Line Breakdown
Let’s walk through the code to understand each part, its input, output, and purpose:

1. **File Creation**:
   - The code is saved in a file named `budget_calculator.py`. This ensures Python recognizes it as a Python script when you run `python budget_calculator.py`.

2. **Single-Line Comment**:
   ```python
   # budget_calculator.py
   # This program manages a simple budget using operators
   ```
   - **Purpose**: These comments, marked with `#`, describe the file and program purpose. They are ignored by Python but help readers understand the code.
   - **Input**: None.
   - **Output**: None (comments don’t produce output).
   - **Side Effects**: None.

3. **Multiline Comment**:
   ```python
   """
   Program: Budget Calculator
   Author: [Your Name]
   Purpose: Uses arithmetic, comparison, logical, and membership operators to manage a budget
   """
   ```
   - **Purpose**: A multiline comment using triple quotes (`"""`) provides detailed documentation, including the program’s name, author, and purpose. Since it’s not assigned to a variable, Python ignores it.
   - **Input**: None.
   - **Output**: None.
   - **Side Effects**: None.

4. **Variable Declarations**:
   ```python
   income = 5000.0  # Float for monthly income
   rent = 1500.0    # Float for rent expense
   groceries = 300.0  # Float for groceries expense
   categories = ["rent", "groceries", "savings"]  # List of expense categories
   ```
   - **Purpose**: Creates four variables:
     - `income`: Stores float `5000.0`. **Input**: `5000.0`. **Output**: None. **Side Effects**: `income` holds `5000.0`.
     - `rent`: Stores float `1500.0`. **Input**: `1500.0`. **Output**: None. **Side Effects**: `rent` holds `1500.0`.
     - `groceries`: Stores float `300.0`. **Input**: `300.0`. **Output**: None. **Side Effects**: `groceries` holds `300.0`.
     - `categories`: Stores list `["rent", "groceries", "savings"]`. **Input**: List of strings. **Output**: None. **Side Effects**: `categories` holds the list.
   - **Comment**: Inline comments explain each variable’s purpose.

5. **Budget Calculations**:
   ```python
   total_expenses = rent + groceries  # Sum of expenses
   savings = income - total_expenses   # Remaining savings
   is_healthy_budget = savings > 0 and savings >= income * 0.2  # Logical check for healthy budget
   ```
   - **Purpose**: Performs arithmetic and logical operations.
   - **Line-by-Line**:
     - `total_expenses = rent + groceries`: Adds `1500.0 + 300.0`. **Input**: `rent`, `groceries`. **Output**: None. **Side Effects**: `total_expenses` holds `1800.0`.
     - `savings = income - total_expenses`: Subtracts `1800.0` from `5000.0`. **Input**: `income`, `total_expenses`. **Output**: None. **Side Effects**: `savings` holds `3200.0`.
     - `is_healthy_budget = savings > 0 and savings >= income * 0.2`: Checks if `savings` is positive (`3200.0 > 0`) and at least 20% of `income` (`3200.0 >= 5000.0 * 0.2 = 1000.0`). Both True, so `and` returns True. **Input**: `savings`, `income`. **Output**: None. **Side Effects**: `is_healthy_budget` holds `True`.

6. **Print Budget Summary**:
   ```python
   print("Budget Summary:")
   print(f"Total Expenses: {total_expenses}")
   print(f"Savings: {savings}")
   print(f"Is budget healthy? {is_healthy_budget}")
   print(f"Is 'savings' in categories? {'savings' in categories}")
   print(f"Is income a float? {isinstance(income, float)}")
   ```
   - **Purpose**: Displays results using f-strings.
   - **Line-by-Line**:
     - `print("Budget Summary:")`: Prints header. **Output**: `Budget Summary:`.
     - `f"Total Expenses: {total_expenses}"`: Embeds `total_expenses`. **Output**: `Total Expenses: 1800.0`.
     - `f"Savings: {savings}"`: Embeds `savings`. **Output**: `Savings: 3200.0`.
     - `f"Is budget healthy? {is_healthy_budget}"`: Embeds `is_healthy_budget`. **Output**: `Is budget healthy? True`.
     - `f"Is 'savings' in categories? {'savings' in categories}"`: Checks if `"savings"` is in `categories`. **Output**: `Is 'savings' in categories? True`.
     - `f"Is income a float? {isinstance(income, float)}"`: Validates `income` type. **Output**: `Is income a float? True`.
   - **Side Effects**: Only printing.

### Visual Description
When you run `python budget_calculator.py` in the terminal, the output is:
```
Budget Summary:
Total Expenses: 1800.0
Savings: 3200.0
Is budget healthy? True
Is 'savings' in categories? True
Is income a float? True
```
The output is a clean, multi-line summary showing calculated values, logical check, membership test, and type validation.

### Common Mistakes and Fixes
1. **Division by Zero**:
   - **Mistake**:
     ```python
     percent_spent = rent / 0  # Invalid division
     ```
   - **Error**: `ZeroDivisionError`.
   - **Fix**: Avoid division by zero; this code doesn’t use division, so safe.
2. **Incorrect Operator Precedence**:
   - **Mistake**:
     ```python
     is_healthy_budget = savings > 0 and savings >= income * 0.2  # Misinterpreting precedence
     ```
   - **Fix**: Multiplication (`income * 0.2`) has higher precedence than comparisons, so no parentheses needed here. For clarity, could write `(savings > 0) and (savings >= income * 0.2)`.
3. **Using `=` Instead of `==`**:
   - **Mistake**:
     ```python
     is_healthy_budget = savings = 0  # Assigns instead of compares
     ```
   - **Error**: Assigns `0` to `savings`, causing incorrect logic.
   - **Fix**: Use `>` and `>=` as shown.
4. **Membership Test with Non-Sequence**:
   - **Mistake**:
     ```python
     print("savings" in income)  # income is a float
     ```
   - **Error**: `TypeError`.
   - **Fix**: Use `categories` (a list) for `in` checks.
5. **Wrong Type for `income`**:
   - **Mistake**:
     ```python
     income = "5000"  # String instead of float
     ```
   - **Error**: `TypeError` in arithmetic operations.
   - **Fix**: Use `5000.0` to ensure float.

### Validation Check
To confirm the program works:
1. Save the code in `budget_calculator.py`.
2. Open a terminal, navigate to the file’s directory, and run `python budget_calculator.py`.
3. Verify the output: `Total Expenses: 1800.0`, `Savings: 3200.0`, `Is budget healthy? True`, `Is 'savings' in categories? True`, `Is income a float? True`.
4. Test with different values (e.g., `income = 4000.0`, `rent = 2000.0`, `groceries = 500.0`) to ensure flexibility. For these values, `savings = 1500.0`, and `is_healthy_budget` should be `True` since `1500.0 >= 4000.0 * 0.2 = 800.0`.
5. Add `print(type(total_expenses))` to confirm it’s a float (`<class 'float'>`).

### Extension Idea Implementation
For learners interested in the extension ideas:
- **Add `is_high_savings`**:
  ```python
  is_high_savings = savings >= income * 0.3  # Check if savings is at least 30% of income
  print(f"Is high savings (30%+)? {is_high_savings}")  # Outputs: True (3200.0 >= 1500.0)
  ```
  - Add after `is_healthy_budget`. Checks if `3200.0 >= 5000.0 * 0.3 = 1500.0`.
- **Calculate percentage of income spent on rent**:
  ```python
  rent_percentage = (rent / income) * 100  # Percentage of income spent on rent
  print(f"Rent percentage: {rent_percentage:.1f}%")  # Outputs: Rent percentage: 30.0%
  ```
  - Add after `savings`. Calculates `(1500.0 / 5000.0) * 100`.

### Research Prompts Answered
- **Why does `is` differ from `==` in Python?**
  - `is` checks if two variables point to the same object in memory (identity), while `==` checks if their values are equal. For example, `x = [1, 2]` and `y = [1, 2]` have equal values (`x == y` is `True`), but different identities (`x is y` is `False`).
- **How does floor division (`//`) differ from regular division (`/`)?
  - Floor division (`//`) returns the largest integer less than or equal to the division result (e.g., `15 // 4 = 3`), while regular division (`/`) returns a float (e.g., `15 / 4 = 3.75`).

### One-Line Takeaway
This program uses arithmetic (`+`, `-`, `*`), comparison (`>`, `>=`), logical (`and`), membership (`in`), and type validation (`isinstance`) to manage a budget and display a formatted summary.