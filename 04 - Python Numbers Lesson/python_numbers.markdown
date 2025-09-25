# Python Numbers Lesson

## Section 1 – Explanations

In Python, numbers are essential for performing calculations and storing numerical data. There are three main numeric types: **int**, **float**, and **complex**. Let’s break down each type and related concepts step by step.

1. **Integers (int)**:
   - An integer is a whole number (no decimals) that can be positive, negative, or zero.
   - Integers have unlimited length in Python, meaning you can work with very large numbers without worrying about size limits.
   - Example:
     ```python
     x = 1
     y = 35656222554887711
     z = -3255522
     print(type(x))  # Output: <class 'int'>
     print(type(y))  # Output: <class 'int'>
     print(type(z))  # Output: <class 'int'>
     ```
   - Here, `x`, `y`, and `z` are integers. The `type()` function confirms they are of type `int`. Integers are useful for counting, indexing, or any situation where decimals aren’t needed.

2. **Floats (float)**:
   - A float is a number that includes decimals, representing fractional values. It can also be positive or negative.
   - Floats can be written in standard decimal form or in scientific notation using `e` to denote powers of 10.
   - Example:
     ```python
     x = 1.10
     y = 1.0
     z = -35.59
     print(type(x))  # Output: <class 'float'>
     print(type(y))  # Output: <class 'float'>
     print(type(z))  # Output: <class 'float'>
     ```
   - Scientific notation example:
     ```python
     a = 35e3   # 35 * 10^3 = 35000.0
     b = 12E4   # 12 * 10^4 = 120000.0
     c = -87.7e100
     print(type(a))  # Output: <class 'float'>
     print(a)       # Output: 35000.0
     ```
   - Floats are ideal for measurements, percentages, or any value requiring precision with decimals.

3. **Complex Numbers (complex)**:
   - Complex numbers have a real part and an imaginary part, denoted by `j` for the imaginary unit.
   - Example:
     ```python
     x = 3 + 5j
     y = 5j
     z = -5j
     print(type(x))  # Output: <class 'complex'>
     print(type(y))  # Output: <class 'complex'>
     print(type(z))  # Output: <class 'complex'>
     ```
   - Complex numbers are used in advanced math, physics, or engineering, but for beginners, just know they combine a real number (like 3) with an imaginary part (like 5j).

4. **Type Conversion**:
   - You can convert between `int`, `float`, and `complex` using the `int()`, `float()`, and `complex()` functions, but you cannot convert a complex number to `int` or `float`.
   - Example:
     ```python
     x = 1      # int
     y = 2.8    # float
     z = 1j     # complex
     a = float(x)    # Convert int to float: 1.0
     b = int(y)      # Convert float to int: 2 (truncates decimal)
     c = complex(x)  # Convert int to complex: (1+0j)
     print(a, type(a))  # Output: 1.0 <class 'float'>
     print(b, type(b))  # Output: 2 <class 'int'>
     print(c, type(c))  # Output: (1+0j) <class 'complex'>
     ```
   - This is useful when you need a specific type for calculations, like converting an integer to a float for division that requires decimals.

5. **Random Numbers**:
   - Python’s `random` module allows you to generate random numbers. The `random.randrange(start, stop)` function generates a random integer from `start` to `stop-1`.
   - Example:
     ```python
     import random
     print(random.randrange(1, 10))  # Outputs a random integer from 1 to 9
     ```
   - This is great for games, simulations, or anything requiring unpredictable numbers.

These concepts are building blocks for calculations and data handling in Python. Understanding how to use and convert numeric types will help you create programs that process numbers effectively.

## Section 2 – Class Exercise

**Exercise: Build a Simple Calculator for a Store Discount**

Let’s create a program that calculates the final price of an item after applying a discount. This exercise reinforces integers, floats, and basic arithmetic.

**Steps**:
1. Ask the user to input the original price of an item (a number with decimals, like 19.99).
2. Ask the user to input a discount percentage (a whole number, like 10 for 10%).
3. Calculate the discount amount using the formula: `discount_amount = original_price * (discount_percentage / 100)`.
4. Calculate the final price: `final_price = original_price - discount_amount`.
5. Print the discount amount and final price, rounded to two decimal places using `round(final_price, 2)`.

**Guidance**:
- Use `float(input())` to get the original price.
- Use `int(input())` to get the discount percentage.
- Perform the calculations using floats to handle decimals.
- Use `print()` to display the results in a clear sentence, like: "The discount is X dollars, and the final price is Y dollars."

Try coding this yourself. If you’re stuck, think about how to store the user’s input as variables and apply the arithmetic operations step by step.

## Section 3 – Weekly Project

**Weekly Project: Personal Budget Tracker**

Create a program that helps a user track their weekly budget by calculating expenses and checking if they’re within their budget. This project combines numbers (integers and floats), user input, and the random module for a fun twist.

**Project Brief**:
- **Goal**: Build a program that asks for a weekly budget, tracks a few expenses, and randomly suggests a small “fun” expense (like a coffee or movie ticket).
- **Milestones**:
  1. Ask the user for their weekly budget (a float, e.g., 100.50).
  2. Ask the user to input three expenses (floats, e.g., groceries, transportation, etc.).
  3. Use the `random.randrange(5, 16)` function to generate a random “fun” expense between $5 and $15.
  4. Calculate the total expenses (sum of the three user inputs plus the random fun expense).
  5. Calculate the remaining budget: `remaining = budget - total_expenses`.
  6. Print a summary showing:
     - The total expenses (rounded to 2 decimal places).
     - The remaining budget (rounded to 2 decimal places).
     - A message saying whether they are under, over, or exactly at their budget.
- **Guidance**:
  - Store the budget and expenses as floats to handle decimals.
  - Use `random.randrange(5, 16)` to add the random expense.
  - Use arithmetic to calculate totals and differences.
  - Use `round(number, 2)` to keep outputs clean.
- **Creative Extension**:
  - Add a feature to let the user categorize their expenses (e.g., “food,” “travel”).
  - Suggest a different random “fun” activity based on the random expense amount (e.g., $5–$8 suggests a coffee, $9–$15 suggests a movie).

This project helps you practice numeric types, basic arithmetic, user input, and the random module while creating something practical and fun. Experiment and make it your own!