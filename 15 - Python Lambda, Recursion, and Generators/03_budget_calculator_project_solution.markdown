# Solution to Personal Budget Calculator Project

This document provides a solution to the **Personal Budget Calculator** project from the Python Lambda, Recursion, and Generators teaching package. It includes the complete code, a detailed explanation, and verification of the expected functionality to help beginners understand and implement the project.

---

## Project Overview

**Objective:**  
Create a Python program that uses lambda functions, recursion, and generators to manage a personal budget. The program collects expenses, calculates the total using recursion, filters expenses by category using a lambda, and displays expenses one at a time using a generator.

**Milestones:**
1. **Input Expenses:** Collect expenses (amount and category) from the user until they type "done", storing them as a list of tuples `(amount, category)`.
2. **Total Expenses (Recursion):** Write a recursive function to sum all expense amounts.
3. **Category Filter (Lambda):** Use a lambda with `filter()` to list expenses in a specific category.
4. **Expense Generator:** Create a generator to yield expenses one at a time for review.

**Deliverables:**
- A Python script that implements all milestones.
- Comments explaining each part of the code.
- The program should run without errors and meet the assessment criteria.

**Expected Functionality:**
- Collects and stores expenses correctly.
- Calculates total expenses using recursion.
- Filters expenses by category using a lambda.
- Yields expenses one by one using a generator.

---

## Solution Code

```python
# Personal Budget Calculator
# This program manages expenses using lambda, recursion, and generators.

# Milestone 1: Input Expenses
def input_expenses():
    """Collects expenses as (amount, category) tuples until user types 'done'."""
    expenses = []
    while True:
        category = input("Enter expense category (or 'done' to finish): ")
        if category.lower() == 'done':
            break
        try:
            amount = float(input("Enter expense amount: "))
            if amount < 0:
                print("Amount cannot be negative. Try again.")
                continue
            expenses.append((amount, category))
        except ValueError:
            print("Invalid amount. Please enter a number.")
    return expenses

# Milestone 2: Total Expenses with Recursion
def total_expenses(expenses):
    """Recursively sums the amounts in the expenses list."""
    if not expenses:  # Base case: empty list
        return 0
    return expenses[0][0] + total_expenses(expenses[1:])  # Recursive case

# Milestone 3: Filter Expenses by Category with Lambda
def filter_by_category(expenses, category):
    """Uses a lambda to filter expenses by category."""
    return list(filter(lambda x: x[1].lower() == category.lower(), expenses))

# Milestone 4: Generator to Yield Expenses
def expense_generator(expenses):
    """Yields expenses one at a time."""
    for expense in expenses:
        yield expense

# Main Program
def main():
    print("Welcome to the Personal Budget Calculator!")
    
    # Collect expenses
    print("\nEnter your expenses:")
    expenses = input_expenses()
    if not expenses:
        print("No expenses entered.")
        return
    
    # Display total expenses
    total = total_expenses(expenses)
    print(f"\nTotal expenses: ${total:.2f}")
    
    # Filter expenses by category
    category = input("\nEnter a category to filter expenses: ")
    filtered_expenses = filter_by_category(expenses, category)
    if filtered_expenses:
        print(f"Expenses in category '{category}':")
        for amount, cat in filtered_expenses:
            print(f"${amount:.2f} - {cat}")
    else:
        print(f"No expenses found in category '{category}'.")
    
    # Display expenses one by one using generator
    print("\nReviewing all expenses one at a time (press Enter to see next, 'q' to quit):")
    gen = expense_generator(expenses)
    for expense in gen:
        print(f"Expense: ${expense[0]:.2f} - {expense[1]}")
        if input().lower() == 'q':
            break

if __name__ == "__main__":
    main()
```

---

## Explanation

### Milestone 1: Input Expenses

**Code Breakdown:**
- **Function**: `input_expenses()`
- **Purpose**: Collects user input for expense amount and category, storing them as tuples in a list.
- **Key Lines**:
  - `while True`: Loops until the user types "done".
  - `category = input(...)`: Gets the expense category.
  - `if category.lower() == 'done'`: Breaks the loop when "done" is entered.
  - `amount = float(input(...))`: Converts the amount to a float, handling invalid inputs with a try-except block.
  - `if amount < 0`: Ensures amounts are non-negative.
  - `expenses.append((amount, category))`: Stores each expense as a tuple `(amount, category)`.
- **Output**: Returns a list of tuples, e.g., `[(50.0, 'Food'), (20.0, 'Travel')]`.

**Why It Works:**
- The function handles user input robustly with error checking for invalid numbers and negative amounts.
- It stores expenses in a structured format (tuples) for easy processing in later steps.

**Common Pitfalls and Fixes:**
- **Pitfall**: User enters non-numeric amounts (e.g., "abc").
  - **Fix**: The try-except block catches `ValueError` and prompts for valid input.
- **Pitfall**: Forgetting to break the loop.
  - **Fix**: The `if category.lower() == 'done'` condition ensures the loop ends.

**Validation Check:**
- Input: `Food, 50`, `Travel, 20`, `done` → Returns `[(50.0, 'Food'), (20.0, 'Travel')]`.

### Milestone 2: Total Expenses with Recursion

**Code Breakdown:**
- **Function**: `total_expenses(expenses)`
- **Purpose**: Recursively sums the amounts in the expenses list.
- **Key Lines**:
  - `if not expenses`: Base case—returns 0 if the list is empty.
  - `expenses[0][0]`: Accesses the amount from the first tuple (e.g., `50.0` from `(50.0, 'Food')`).
  - `total_expenses(expenses[1:])`: Recursive call with the rest of the list.
  - `return expenses[0][0] + total_expenses(...)`: Adds the first amount to the sum of the rest.

**Why It Works:**
- The recursion breaks the problem into smaller parts, summing one amount at a time.
- The base case prevents infinite recursion for an empty list.

**Common Pitfalls and Fixes:**
- **Pitfall**: Missing base case, causing infinite recursion.
  - **Fix**: The `if not expenses` condition stops recursion.
- **Pitfall**: Incorrectly accessing tuple elements (e.g., `expenses[0]` instead of `expenses[0][0]`).
  - **Fix**: Use `expenses[0][0]` to get the amount from the tuple.

**Validation Check:**
- For `[(50.0, 'Food'), (20.0, 'Travel')]`, returns `50.0 + 20.0 = 70.0`.

### Milestone 3: Filter Expenses by Category with Lambda

**Code Breakdown:**
- **Function**: `filter_by_category(expenses, category)`
- **Purpose**: Filters expenses by a specified category using a lambda with `filter()`.
- **Key Lines**:
  - `lambda x: x[1].lower() == category.lower()`: Checks if the expense’s category (`x[1]`) matches the input category (case-insensitive).
  - `filter(...)`: Applies the lambda to each expense tuple, keeping those that match.
  - `list(filter(...))`: Converts the filter object to a list.

**Why It Works:**
- The lambda function simplifies the filtering logic into a single expression.
- Case-insensitive comparison (`lower()`) makes the filter user-friendly.

**Common Pitfalls and Fixes:**
- **Pitfall**: Case sensitivity in category matching.
  - **Fix**: Use `lower()` for both the expense category and input category.
- **Pitfall**: Forgetting to convert `filter()` output to a list.
  - **Fix**: Use `list()` to make the output usable.

**Validation Check:**
- For `[(50.0, 'Food'), (20.0, 'Travel'), (30.0, 'Food')]`, filtering by "Food" returns `[(50.0, 'Food'), (30.0, 'Food')]`.

### Milestone 4: Expense Generator

**Code Breakdown:**
- **Function**: `expense_generator(expenses)`
- **Purpose**: Yields expenses one at a time for review.
- **Key Lines**:
  - `for expense in expenses`: Loops through the expenses list.
  - `yield expense`: Yields each tuple, pausing the function until the next call.

**Why It Works:**
- The generator yields one expense at a time, making it memory-efficient.
- The main program uses the generator interactively, allowing the user to control the pace.

**Common Pitfalls and Fixes:**
- **Pitfall**: Trying to print the generator directly (prints a generator object).
  - **Fix**: Iterate with a `for` loop or `next()` to access yielded values.
- **Pitfall**: Reusing an exhausted generator.
  - **Fix**: Create a new generator instance if needed.

**Validation Check:**
- For `[(50.0, 'Food'), (20.0, 'Travel')]`, yields `(50.0, 'Food')`, then `(20.0, 'Travel')`.

### Main Program

**Code Breakdown:**
- **Function**: `main()`
- **Purpose**: Orchestrates the program flow, calling each function and displaying results.
- **Key Steps**:
  - Calls `input_expenses()` to collect expenses.
  - Uses `total_expenses()` to compute the total.
  - Prompts for a category and uses `filter_by_category()` to show matching expenses.
  - Uses `expense_generator()` to review expenses one at a time, with an option to quit.

**Sample Run:**
```
Welcome to the Personal Budget Calculator!

Enter your expenses:
Enter expense category (or 'done' to finish): Food
Enter expense amount: 50
Enter expense category (or 'done' to finish): Travel
Enter expense amount: 20
Enter expense category (or 'done' to finish): Food
Enter expense amount: 30
Enter expense category (or 'done' to finish): done

Total expenses: $100.00

Enter a category to filter expenses: Food
Expenses in category 'Food':
$50.00 - Food
$30.00 - Food

Reviewing all expenses one at a time (press Enter to see next, 'q' to quit):
Expense: $50.00 - Food

Expense: $20.00 - Travel

Expense: $30.00 - Food
q
```

---

## Assessment Criteria Check

- **Collects and stores expenses**: `input_expenses()` stores expenses as a list of tuples.
- **Recursive total**: `total_expenses()` correctly sums amounts using recursion.
- **Lambda filter**: `filter_by_category()` uses a lambda to filter by category.
- **Generator**: `expense_generator()` yields expenses one at a time.
- **Error-free and commented**: The code runs without errors and includes clear comments.

---

## Completion Checklist

- [x] Implemented `input_expenses()` to collect and store expenses.
- [x] Wrote `total_expenses()` to recursively sum amounts.
- [x] Created `filter_by_category()` using a lambda with `filter()`.
- [x] Built `expense_generator()` to yield expenses one by one.
- [x] Integrated all parts in `main()` with user-friendly output.
- [x] Included comments explaining each function.
- [x] Avoided common pitfalls like missing base cases or incorrect lambda syntax.

**One-Line Takeaway:**  
The Personal Budget Calculator uses lambda functions, recursion, and generators to efficiently manage and analyze expenses in a user-friendly way.