# Solution to Weekly Project: Personal Budget Tracker

This document provides a solution to the "Personal Budget Tracker" project, which helps beginners practice using variables, basic arithmetic, and outputting data in Python. Below is an explanation of the solution, followed by the complete code.

## Explanation

The project requires creating a Python program that tracks weekly expenses for three categories: food, transport, and entertainment. The program should:
1. Store expenses in variables (using integers or floats).
2. Calculate the total expenses by adding the variables.
3. Display a summary of individual expenses and the total in a clear sentence.
4. Use appropriate variable names (e.g., `food_expense`).
5. Output the summary using either commas or the `+` operator for string concatenation.

### Key Concepts Applied
- **Variable Creation**: Use variables to store expense amounts, following snake_case naming conventions for readability.
- **Arithmetic Operations**: Add the expense variables to calculate the total.
- **Output with `print()`**:
  - Using commas in `print()` handles different data types (e.g., floats and strings) and adds spaces automatically.
  - Using the `+` operator requires casting numbers to strings with `str()` for concatenation.
- **Casting**: Convert numeric values to strings when using `+` to combine with text.
- **Real-World Context**: The project mimics a practical scenario, reinforcing how variables can organize and display meaningful data.

### Step-by-Step Solution
1. **Define Expense Variables**:
   - Create `food_expense`, `transport_expense`, and `entertainment_expense` as floats (e.g., `50.25`, `30.0`, `20.75`) to represent realistic monetary values.
2. **Calculate Total**:
   - Create a `total_expense` variable by adding the three expense variables.
3. **Output Using Commas**:
   - Use `print()` with commas to display a summary sentence, as commas handle floats and strings seamlessly.
4. **Output Using `+`**:
   - Use `print()` with the `+` operator, casting each float to a string with `str()` to concatenate them into a sentence.
5. **Test the Program**:
   - Ensure the total is calculated correctly and the output is clear and readable.

### Why This Works
- **Variables**: Using descriptive names like `food_expense` makes the code intuitive and mirrors real-world budgeting.
- **Arithmetic**: Adding floats ensures accurate calculations for monetary values.
- **Output Flexibility**: Showing both comma-based and `+`-based `print()` statements reinforces the difference between these methods.
- **Beginner-Friendly**: The code is simple, uses only variables and basic operations, and produces a practical output, building confidence.
- **Extensibility**: The structure hints at future concepts like conditionals (e.g., checking if spending exceeds a budget) or lists (e.g., storing expenses in a collection).

## Solution Code

Below is the complete Python code for the project, implementing all requirements.

```python
# Define expense variables with sample values (in dollars)
food_expense = 50.25
transport_expense = 30.0
entertainment_expense = 20.75

# Calculate the total expenses
total_expense = food_expense + transport_expense + entertainment_expense

# Output using commas (handles floats and adds spaces automatically)
print("This week, you spent $", food_expense, "on food, $", transport_expense, "on transport, $", entertainment_expense, "on entertainment, totaling $", total_expense, ".", sep="")

# Output using + operator (requires casting floats to strings)
print("This week, you spent $" + str(food_expense) + " on food, $" + str(transport_expense) + " on transport, $" + str(entertainment_expense) + " on entertainment, totaling $" + str(total_expense) + ".")
```

### Expected Output
```
This week, you spent $50.25 on food, $30.0 on transport, $20.75 on entertainment, totaling $101.0.
This week, you spent $50.25 on food, $30.0 on transport, $20.75 on entertainment, totaling $101.0.
```

### Notes for Beginners
- **Variable Names**: Using `food_expense` instead of `x` makes the code self-explanatory.
- **Floats for Money**: Floats (e.g., `50.25`) are used because expenses often include cents.
- **Comma vs. `+` in `print()`**:
  - Commas are easier since they don’t require casting and add spaces automatically. The `sep=""` parameter removes extra spaces for cleaner output.
  - The `+` operator requires casting floats to strings (e.g., `str(food_expense)`) and manual spacing in the text.
- **Testing**: Try changing the expense values (e.g., `food_expense = 75.5`) and run the program to see updated totals.
- **Extension Ideas**:
  - Add a `budget` variable and print a message if `total_expense` exceeds it (hint: this uses conditionals, a future topic).
  - Format the output to align numbers like a receipt (e.g., using string formatting, another future topic).

This solution reinforces variables, basic arithmetic, and output in a practical context, encouraging beginners to experiment with their own expense values and explore creative extensions.