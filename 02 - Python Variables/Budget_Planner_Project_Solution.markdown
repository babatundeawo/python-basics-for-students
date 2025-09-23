# Solution to Weekly Project: Personal Budget Planner

## Explanation

The **Personal Budget Planner** project requires creating a Python program to track monthly expenses for three categories, calculate the total and average spending, and display the results in a clear format. The solution uses variables to store expense categories and their costs, multiple value assignments for efficiency, and the `print()` function with commas to output information safely. It employs **snake_case** for variable names to enhance readability, as recommended for multi-word variables, and includes a header to make the output user-friendly.

The project steps are:
1. Use multiple variable assignment to create three variables for expense categories and their costs.
2. Calculate the total spending by adding the expense values.
3. Calculate the average spending by dividing the total by 3.
4. Print each category and its cost in a readable format.
5. Print the total and average spending with clear labels.

This solution is designed to be beginner-friendly, using concepts from the variables lesson (variable creation, multiple assignments, output formatting, and basic arithmetic) while avoiding advanced features like lists. The code is tested to ensure accurate calculations and clear output.

## Solution Code

```python
# Step 1: Assign expense categories and costs
food, transport, entertainment = 200, 150, 100

# Step 2: Calculate total spending
total_spending = food + transport + entertainment

# Step 3: Calculate average spending
average_spending = total_spending / 3

# Step 4: Print header and each category with its cost
print("Monthly Budget Summary")
print("---------------------")
print("Food:", food)
print("Transport:", transport)
print("Entertainment:", entertainment)

# Step 5: Print total and average spending
print("---------------------")
print("Total Spending:", total_spending)
print("Average Spending per Category:", average_spending)
```

## Explanation of the Code

- **Multiple Variable Assignment**:
  - The line `food, transport, entertainment = 200, 150, 100` assigns three expense categories and their costs in one line, using the multiple assignment technique from the lesson. This is efficient and clear for beginners.
  - The variables `food`, `transport`, and `entertainment` are given integer values (200, 150, 100) for simplicity, though floats could be used for more precise budgeting.

- **Calculations**:
  - `total_spending = food + transport + entertainment` uses the `+` operator to sum the expenses, storing the result (450) in `total_spending`.
  - `average_spending = total_spending / 3` calculates the average by dividing the total by the number of categories (3), resulting in 150.0 (a float due to division).

- **Output Formatting**:
  - A header ("Monthly Budget Summary") and dashed lines ("---------------------") are printed to make the output visually appealing and organized.
  - Each expense category is printed using `print()` with commas (e.g., `print("Food:", food)`), which safely combines strings and numbers, avoiding errors that would occur with `+` concatenation.
  - The total and average spending are printed with clear labels for readability.

- **Variable Naming**:
  - Snake_case (e.g., `total_spending`, `average_spending`) is used for multi-word variable names, following one of the naming conventions from the lesson, making the code easy to read.

## Expected Output

When you run the code, it will produce:

```
Monthly Budget Summary
---------------------
Food: 200
Transport: 150
Entertainment: 100
---------------------
Total Spending: 450
Average Spending per Category: 150.0
```

This output is clear, well-organized, and meets the project requirements. It displays each category’s cost, the total spending, and the average spending in a beginner-friendly format. The use of a header and separators enhances readability, and the code encourages experimentation with different expense values or naming conventions (e.g., camelCase) as suggested in the project brief.

## Notes for Exploration
- The project brief nudges students to consider storing expenses in a list for future lessons. This solution avoids lists to stay within the scope of variables but sets the stage for exploring collections later.
- Beginners can test the code with different expense values (e.g., 250.5, 175.25, 120) to verify calculations and practice modifying variables.