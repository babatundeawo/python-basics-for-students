# Solution to Class Exercise: Write and Run a Simple Python Program

This document provides a sample solution to the class exercise described in the Python Syntax lesson. The exercise involves creating a Python program named `greeting.py` that uses variables, proper indentation, and comments to display a greeting based on a condition. The solution follows the guidelines, ensuring it is beginner-friendly and includes all required elements without providing excessive complexity.

## Sample Solution

Below is a Python program that meets the exercise requirements. It includes a variable, an `if` statement with proper indentation, and comments to explain the code. The program checks if a number is greater than 5 and prints a message accordingly.

```python
# This program checks a number and prints a greeting if it is greater than 5
number = 7  # Create a variable with a value between 1 and 10

if number > 5:  # Check if the number is greater than 5
    # Print a message if the condition is true
    print("Number is large!")
```

### Explanation of the Solution
- **Comment**: The line `# This program checks a number and prints a greeting if it is greater than 5` explains the program’s purpose.
- **Variable**: `number = 7` assigns the value `7` to the variable `number`.
- **If Statement**: The condition `if number > 5:` checks if the number is greater than 5.
- **Indentation**: The `print("Number is large!")` line is indented with 4 spaces, as required by Python to indicate it belongs to the `if` block.
- **Comment in Block**: The line `# Print a message if the condition is true` inside the `if` block explains the action.
- **Running the Program**: Save this code in a file named `greeting.py` and run it with `python greeting.py`. For `number = 7`, the output will be `Number is large!`. If you change `number` to a value like `3`, no output will appear because the condition is false.

### Testing Variations
To complete the exercise, you can modify the `number` variable (e.g., set it to `2`, `5`, or `10`) and rerun the program to observe how the output changes based on the condition.