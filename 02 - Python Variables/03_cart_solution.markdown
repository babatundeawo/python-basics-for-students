# Solution to Python Weekly Project: Shopping Cart Summary

This document provides the solution to the Python weekly project from the Python Variables tutorial, where the task is to create a program that generates a shopping cart summary using variables, multiple assignments, and scope. Below is the solution code, followed by a detailed explanation tailored for beginners.

---

## Solution Code

```python
# cart.py
# This program generates a shopping cart summary with global and local variables

"""
Program: Shopping Cart Summary
Author: [Your Name]
Purpose: Uses multiple assignments and scope to display global and local cart summaries
"""

# Declare global variables using multiple assignment
item1, item2, item3 = "Apple", "Banana", "Orange"  # Global cart items
price1, price2, price3 = 0.5, 0.3, 0.6  # Global item prices
total = price1 + price2 + price3  # Sum of global prices

# Define function to print local cart
def print_cart():
    # Local variables with different values
    item1, item2, item3 = "Bread", "Milk", "Eggs"  # Local cart items
    print("Local Cart:", item1, ",", item2, ",", item3)  # Print local summary

# Call the function to print local cart
print_cart()

# Print global cart summary
print("Global Cart:", item1, ",", item2, ",", item3, ", Total:", total)
```

**Expected Output**:
```
Local Cart: Bread , Milk , Eggs
Global Cart: Apple , Banana , Orange , Total: 1.4
```

---

## Explanation

### Objective
The project requires creating a Python program (`cart.py`) that:
- Declares global variables for three items (`item1`, `item2`, `item3`) and their prices (`price1`, `price2`, `price3`) using multiple assignment.
- Calculates a global `total` as the sum of prices.
- Defines a function `print_cart()` that uses local variables with the same names but different values to print a local cart summary.
- Prints a global cart summary outside the function, including the total.
- Includes comments to explain each section.
- Uses snake_case for variable names and runs correctly with `python cart.py`.

### Line-by-Line Breakdown
Let’s walk through the code to understand each part, its input, output, and purpose:

1. **File Creation**:
   - The code is saved in a file named `cart.py`. This ensures Python recognizes it as a Python script when you run `python cart.py`.

2. **Single-Line Comment**:
   ```python
   # cart.py
   # This program generates a shopping cart summary with global and local variables
   ```
   - **Purpose**: These comments, marked with `#`, describe the file and program purpose. They are ignored by Python but help readers understand the code.
   - **Input**: None.
   - **Output**: None (comments don’t produce output).
   - **Side Effects**: None.

3. **Multiline Comment**:
   ```python
   """
   Program: Shopping Cart Summary
   Author: [Your Name]
   Purpose: Uses multiple assignments and scope to display global and local cart summaries
   """
   ```
   - **Purpose**: A multiline comment using triple quotes (`"""`) provides detailed documentation, including the program’s name, author, and purpose. Since it’s not assigned to a variable, Python ignores it.
   - **Input**: None.
   - **Output**: None.
   - **Side Effects**: None.

4. **Global Variable Declarations**:
   ```python
   item1, item2, item3 = "Apple", "Banana", "Orange"  # Global cart items
   price1, price2, price3 = 0.5, 0.3, 0.6  # Global item prices
   total = price1 + price2 + price3  # Sum of global prices
   ```
   - **Purpose**: Declares global variables using multiple assignment and calculates their total:
     - `item1, item2, item3 = "Apple", "Banana", "Orange"`: Assigns strings to three variables in one line. **Input**: `"Apple"`, `"Banana"`, `"Orange"`. **Output**: None. **Side Effects**: `item1 = "Apple"`, `item2 = "Banana"`, `item3 = "Orange"`.
     - `price1, price2, price3 = 0.5, 0.3, 0.6`: Assigns float values for prices. **Input**: `0.5`, `0.3`, `0.6`. **Output**: None. **Side Effects**: `price1 = 0.5`, `price2 = 0.3`, `price3 = 0.6`.
     - `total = price1 + price2 + price3`: Adds the prices to compute `total = 1.4`. **Input**: `price1`, `price2`, `price3`. **Output**: None. **Side Effects**: `total = 1.4`.
   - **Comment**: Inline comments explain the purpose of each line.

5. **Function Definition with Local Variables**:
   ```python
   def print_cart():
       # Local variables with different values
       item1, item2, item3 = "Bread", "Milk", "Eggs"  # Local cart items
       print("Local Cart:", item1, ",", item2, ",", item3)  # Print local summary
   ```
   - **Purpose**: Defines a function `print_cart()` that creates local variables with the same names as global ones but different values, then prints a local cart summary.
   - **Line-by-Line**:
     - `def print_cart():`: Defines the function. The colon `:` signals a new block.
     - `item1, item2, item3 = "Bread", "Milk", "Eggs"`: Creates local variables, shadowing global ones. **Input**: `"Bread"`, `"Milk"`, `"Eggs"`. **Output**: None. **Side Effects**: Local `item1 = "Bread"`, `item2 = "Milk"`, `item3 = "Eggs"`.
     - `print("Local Cart:", item1, ",", item2, ",", item3)`: Prints the local cart using commas for spacing. **Input**: Local `item1`, `item2`, `item3`, and strings. **Output**: `Local Cart: Bread , Milk , Eggs`. **Side Effects**: Only printing.
   - **Indentation**: Lines inside the function are indented with 4 spaces to define the function’s scope.

6. **Function Call**:
   ```python
   print_cart()  # Call the function to print local cart
   ```
   - **Purpose**: Executes `print_cart()`, printing the local cart summary.
   - **Input**: None.
   - **Output**: `Local Cart: Bread , Milk , Eggs`.
   - **Side Effects**: None beyond printing.

7. **Global Cart Summary**:
   ```python
   print("Global Cart:", item1, ",", item2, ",", item3, ", Total:", total)
   ```
   - **Purpose**: Prints the global cart summary using global variables.
   - **Input**: Global `item1` (`"Apple"`), `item2` (`"Banana"`), `item3` (`"Orange"`), `total` (`1.4`), and strings.
   - **Output**: `Global Cart: Apple , Banana , Orange , Total: 1.4`.
   - **Side Effects**: Only printing.
   - **Explanation**: Uses global variables, unaffected by the local variables in `print_cart()`.

### Visual Description
When you run `python cart.py` in the terminal, the output is:
```
Local Cart: Bread , Milk , Eggs
Global Cart: Apple , Banana , Orange , Total: 1.4
```
Each line is printed in the terminal, with commas in `print()` adding spaces for readability.

### Common Mistakes and Fixes
1. **Mismatched Variables in Multiple Assignment**:
   - **Mistake**:
     ```python
     item1, item2 = "Apple", "Banana", "Orange"  # Too many values
     ```
   - **Error**: `ValueError: too many values to unpack`.
   - **Fix**: Ensure the number of variables matches the values: `item1, item2, item3 = "Apple", "Banana", "Orange"`.
2. **Invalid Variable Names**:
   - **Mistake**: Using `item-1` or `1item`.
   - **Error**: `SyntaxError: invalid syntax`.
   - **Fix**: Use snake_case, e.g., `item_1`.
3. **Modifying Global Variables Without `global`**:
   - **Mistake**:
     ```python
     def print_cart():
         item1 = "Bread"  # Creates local variable
     print_cart()
     print(item1)  # Uses global item1
     ```
   - **Fix**: Local variables don’t affect globals unless `global` is used (not needed here since local scope is intentional).
4. **Incorrect Price Summation**:
   - **Mistake**: Using strings for prices, e.g., `price1 = "0.5"`.
   - **Error**: `TypeError` if trying to add strings.
   - **Fix**: Use floats, e.g., `price1 = 0.5`.
5. **Wrong File Extension**:
   - **Mistake**: Saving as `cart.txt`.
   - **Fix**: Save as `cart.py` and run with `python cart.py`.

### Validation Check
To confirm the program works:
1. Save the code in `cart.py`.
2. Open a terminal, navigate to the file’s directory, and run `python cart.py`.
3. Verify the output matches: `Local Cart: Bread , Milk , Eggs` followed by `Global Cart: Apple , Banana , Orange , Total: 1.4`.
4. Test with different items and prices (e.g., `item1, item2, item3 = "Pen", "Book", "Ruler"`, `price1, price2, price3 = 1.0, 2.5, 0.8`) to ensure flexibility.
5. Add `print(item1)` after `print_cart()` to confirm global `item1` remains `"Apple"`.

### Extension Idea Implementation
For learners interested in the extension ideas:
- **Add a `discount` variable**:
  ```python
  discount = 0.1  # 10% discount
  total = total * (1 - discount)  # Apply discount to total
  ```
  - Add before the global summary to reduce `total` (e.g., `1.4 * 0.9 = 1.26`).
- **Use `global` keyword**:
  ```python
  def print_cart():
      global total
      item1, item2, item3 = "Bread", "Milk", "Eggs"
      total = 2.0  # Modify global total
      print("Local Cart:", item1, ",", item2, ",", item3)
  ```
  - This changes `total` globally, so the global summary reflects `total = 2.0`.

### Research Prompts Answered
- **How does the `+` operator behave differently for strings vs. numbers?**
  - For strings, `+` concatenates (e.g., `"Apple" + "Banana" = "AppleBanana"`).
  - For numbers, `+` adds (e.g., `0.5 + 0.3 = 0.8`).
- **What happens if you try to modify a global variable without the `global` keyword?**
  - Python creates a local variable instead, leaving the global variable unchanged.

### One-Line Takeaway
This program uses multiple assignments, global/local scope, and comma-separated `print()` to display a shopping cart summary, reinforcing Python’s variable handling and function scope.