# Solution to Python Class Exercise: Personalized Greeting

This document provides the solution to the Python class exercise from the Python Introduction tutorial, where the task is to create a program that uses variables, comments, and proper indentation to display a personalized greeting based on age. Below is the solution code, followed by a detailed explanation tailored for beginners.

---

## Solution Code

```python
# greeting.py
# This program creates a personalized greeting based on the user's age

"""
Program: Personalized Greeting
Author: [Your Name]
Purpose: Uses variables and conditionals to print a greeting
"""

# Declare variables for name and age
name = "Alice"  # Store the user's name as a string
age = 20  # Store the user's age as an integer

# Check if the user is an adult (age >= 18)
if age >= 18:
    print(f"Hello, {name}! You are an adult.")  # Print adult greeting
else:
    print(f"Hello, {name}! You are not yet an adult.")  # Print minor greeting
```

**Expected Output** (for `name = "Alice"`, `age = 20`):
```
Hello, Alice! You are an adult.
```

---

## Explanation

### Objective
The exercise requires creating a Python program (`greeting.py`) that:
- Declares two variables: `name` (a string) and `age` (an integer).
- Uses an `if` statement to check if `age` is greater than or equal to 18.
- Prints a personalized greeting based on the age condition.
- Includes single-line and multiline comments for clarity.
- Uses proper indentation to avoid syntax errors.

### Line-by-Line Breakdown
Let’s walk through the code to understand each part, its input, output, and purpose:

1. **File Creation**:
   - The code is saved in a file named `greeting.py`. This ensures Python recognizes it as a Python script when you run `python greeting.py`.

2. **Single-Line Comment**:
   ```python
   # greeting.py
   # This program creates a personalized greeting based on the user's age
   ```
   - **Purpose**: The `#` marks a comment, ignored by Python but helpful for readers. These lines describe the file and program purpose.
   - **Input**: None.
   - **Output**: None (comments don’t produce output).
   - **Side Effects**: None.

3. **Multiline Comment**:
   ```python
   """
   Program: Personalized Greeting
   Author: [Your Name]
   Purpose: Uses variables and conditionals to print a greeting
   """
   ```
   - **Purpose**: A multiline comment using triple quotes (`"""`) provides detailed documentation, such as the program’s name, author, and purpose. Since it’s not assigned to a variable, Python ignores it.
   - **Input**: None.
   - **Output**: None.
   - **Side Effects**: None.

4. **Variable Declarations**:
   ```python
   name = "Alice"  # Store the user's name as a string
   age = 20  # Store the user's age as an integer
   ```
   - **Purpose**: Creates two variables:
     - `name`: Stores the string `"Alice"`. Strings are text enclosed in quotes (`"` or `'`).
     - `age`: Stores the integer `20`. Integers are whole numbers without quotes.
   - **Input**: The values `"Alice"` and `20`.
   - **Output**: None (assigning values doesn’t produce output).
   - **Side Effects**: Stores `"Alice"` in `name` and `20` in `age` for later use.
   - **Comment**: Inline comments (`# Store...`) explain what each variable does.

5. **Conditional Statement**:
   ```python
   if age >= 18:
       print(f"Hello, {name}! You are an adult.")  # Print adult greeting
   else:
       print(f"Hello, {name}! You are not yet an adult.")  # Print minor greeting
   ```
   - **Purpose**: Checks if `age` is greater than or equal to 18 and prints a message accordingly.
   - **Line-by-Line**:
     - `if age >= 18:`: Tests if `age` (20) is at least 18. The condition evaluates to `True` (since 20 ≥ 18). The colon `:` signals a new code block.
     - `print(f"Hello, {name}! You are an adult.")`: Executes if the condition is `True`. Uses an f-string (`f"..."`) to insert `name` into the message. Indented with 4 spaces to indicate it’s part of the `if` block.
       - **Input**: The value of `name` (`"Alice"`) and the string template.
       - **Output**: `Hello, Alice! You are an adult.`.
     - `else:`: Defines what happens if the condition is `False` (i.e., `age < 18`). The colon `:` signals another block.
     - `print(f"Hello, {name}! You are not yet an adult.")`: Executes if `age < 18`. Indented with 4 spaces. In this case, it doesn’t run since `age` is 20.
       - **Input**: The value of `name` and the string template.
       - **Output**: None (since the condition is `True`).
     - **Side Effects**: Only the printing of the message occurs.
     - **Comments**: Inline comments clarify which message is printed for each case.

6. **Indentation**:
   - The `print` statements are indented with 4 spaces under `if` and `else`. This tells Python they belong to those blocks. Without proper indentation, Python raises a `SyntaxError`.

### Visual Description
When you run `python greeting.py` in the terminal (with `name = "Alice"`, `age = 20`):
- The terminal displays: `Hello, Alice! You are an adult.` on a single line.
- If you change `age` to 15, it displays: `Hello, Alice! You are not yet an adult.`

### Common Mistakes and Fixes
1. **Forgetting Indentation**:
   - **Mistake**:
     ```python
     if age >= 18:
     print(f"Hello, {name}! You are an adult.")  # No indentation
     ```
   - **Error**: `SyntaxError: expected an indented block`.
   - **Fix**: Add 4 spaces before the `print` statement to align it with the `if` block.
2. **Missing Colon (`:`)**:
   - **Mistake**:
     ```python
     if age >= 18
         print(f"Hello, {name}! You are an adult.")
     ```
   - **Error**: `SyntaxError: invalid syntax`.
   - **Fix**: Add a colon after the `if` condition: `if age >= 18:`.
3. **Invalid Variable Name**:
   - **Mistake**: Using `1name` or `$name` instead of `name`.
   - **Error**: `SyntaxError: invalid syntax`.
   - **Fix**: Use valid names (letters, numbers, underscores; starting with a letter or underscore).
4. **Incorrect File Extension**:
   - **Mistake**: Saving as `greeting.txt` instead of `greeting.py`.
   - **Fix**: Save with the `.py` extension and run with `python greeting.py`.

### Validation Check
To confirm the program works:
1. Save the code in `greeting.py`.
2. Open a terminal, navigate to the file’s directory, and run `python greeting.py`.
3. Verify the output matches the expected message based on `age`.
4. Test with a different `age` (e.g., 15) to ensure the `else` block works.

### One-Line Takeaway
This program uses variables, conditionals, and comments to print a personalized greeting, demonstrating Python’s simple syntax and the importance of indentation.