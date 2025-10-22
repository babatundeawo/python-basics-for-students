# Solution to Python Class Exercise: Text Formatter

This document provides the solution to the Python class exercise from the Python Decorators tutorial, where the task is to create a program that uses decorators to format text output from functions. Below is the solution code, followed by a detailed explanation tailored for beginners.

---

## Solution Code

```python
# text_formatter.py
# This program uses decorators to format text output from functions

"""
Program: Text Formatter
Author: [Your Name]
Purpose: Demonstrates using decorators to modify function output with uppercase and custom prefixes
"""

import functools

# Decorator to convert output to uppercase
def uppercase(func):
    @functools.wraps(func)
    def wrapper(*args, **kwargs):
        return func(*args, **kwargs).upper()
    return wrapper

# Decorator factory to add a custom prefix
def add_prefix(s):
    def decorator(func):
        @functools.wraps(func)
        def wrapper(*args, **kwargs):
            return f"{s}{func(*args, **kwargs)}"
        return wrapper
    return decorator

# Function to return a greeting
@uppercase
def greet(name):
    """Returns a greeting for the given name."""
    return f"Hello {name}"

# Function to return a comma-separated list of items
@add_prefix("Items: ")
def describe(*items):
    """Returns a comma-separated list of items."""
    return ", ".join(items)

# Main program
print("Greet:")
print(greet("John"))

print("Describe:")
print(describe("apple", "banana", "cherry"))

print("Function Names:")
print(greet.__name__)
print(describe.__name__)
```

**Expected Output**:
```
Greet:
HELLO JOHN
Describe:
Items: APPLE, BANANA, CHERRY
Function Names:
greet
describe
```

---

## Explanation

### Objective
The exercise requires creating a Python program (`text_formatter.py`) that:
- Defines a decorator `uppercase` to convert function output to uppercase.
- Defines a decorator factory `add_prefix(s)` to add a custom prefix to the output.
- Defines a function `greet(name)` to return a greeting.
- Defines a function `describe(*items)` to return a comma-separated list of items.
- Applies `@uppercase` to `greet` and `@add_prefix("Items: ")` to `describe`.
- Uses `functools.wraps` to preserve metadata.
- Calls functions with sample inputs and verifies function names.
- Includes comments to explain each step.
- Runs correctly with `python text_formatter.py`.

### Line-by-Line Breakdown
Let’s walk through the code to understand each part, its input, output, and purpose:

1. **File Creation**:
   - The code is saved in a file named `text_formatter.py`. This ensures Python recognizes it as a Python script when you run `python text_formatter.py`.

2. **Single-Line Comment**:
   ```python
   # text_formatter.py
   # This program uses decorators to format text output from functions
   ```
   - **Purpose**: Describes the file and program purpose. Ignored by Python.
   - **Input**: None.
   - **Output**: None.
   - **Side Effects**: None.

3. **Multiline Comment**:
   ```python
   """
   Program: Text Formatter
   Author: [Your Name]
   Purpose: Demonstrates using decorators to modify function output with uppercase and custom prefixes
   """
   ```
   - **Purpose**: Provides detailed documentation. Ignored by Python since it’s not assigned.
   - **Input**: None.
   - **Output**: None.
   - **Side Effects**: None.

4. **Import functools**:
   ```python
   import functools
   ```
   - **Purpose**: Imports `functools` for `wraps` to preserve function metadata.
   - **Input**: None.
   - **Output**: None.
   - **Side Effects**: Makes `functools.wraps` available.

5. **Decorator: uppercase**:
   ```python
   def uppercase(func):
       @functools.wraps(func)
       def wrapper(*args, **kwargs):
           return func(*args, **kwargs).upper()
       return wrapper
   ```
   - **Purpose**: Converts function output to uppercase.
   - **Input**: `func` (function to decorate).
   - **Output**: Wrapper function that uppercases output.
   - **Side Effects**: None.
   - **Explanation**:
     - `@functools.wraps(func)`: Preserves metadata of `func`.
     - `def wrapper(*args, **kwargs)`: Accepts any arguments.
     - `func(*args, **kwargs).upper()`: Calls original function and uppercases result.
     - `return wrapper`: Returns wrapper function.

6. **Decorator Factory: add_prefix**:
   ```python
   def add_prefix(s):
       def decorator(func):
           @functools.wraps(func)
           def wrapper(*args, **kwargs):
               return f"{s}{func(*args, **kwargs)}"
           return wrapper
       return decorator
   ```
   - **Purpose**: Adds a custom prefix to function output.
   - **Input**: `s` (prefix string), `func` (function to decorate).
   - **Output**: Wrapper function that prepends `s`.
   - **Side Effects**: None.
   - **Explanation**:
     - `def add_prefix(s)`: Factory takes prefix `s`.
     - `def decorator(func)`: Decorator takes function.
     - `@functools.wraps(func)`: Preserves metadata.
     - `f"{s}{func(*args, **kwargs)}"`: Prepends prefix to function output.
     - `return decorator`: Returns decorator function.

7. **Function: greet**:
   ```python
   @uppercase
   def greet(name):
       """Returns a greeting for the given name."""
       return f"Hello {name}"
   ```
   - **Purpose**: Returns a greeting string, decorated to be uppercase.
   - **Input**: `name` (string, e.g., `"John"`).
   - **Output**: Uppercase greeting (e.g., `HELLO JOHN`).
   - **Side Effects**: None.
   - **Explanation**:
     - `@uppercase`: Applies `uppercase` decorator.
     - `return f"Hello {name}"`: Returns greeting string.
     - Docstring documents function purpose.

8. **Function: describe**:
   ```python
   @add_prefix("Items: ")
   def describe(*items):
       """Returns a comma-separated list of items."""
       return ", ".join(items)
   ```
   - **Purpose**: Returns a comma-separated list of items with a prefix.
   - **Input**: `*items` (variable number of strings, e.g., `"apple", "banana", "cherry"`).
   - **Output**: Prefixed string (e.g., `Items: APPLE, BANANA, CHERRY`).
   - **Side Effects**: None.
   - **Explanation**:
     - `@add_prefix("Items: ")`: Applies prefix decorator.
     - `", ".join(items)`: Joins items with commas.
     - Docstring documents function purpose.

9. **Main Program**:
   ```python
   print("Greet:")
   print(greet("John"))

   print("Describe:")
   print(describe("apple", "banana", "cherry"))

   print("Function Names:")
   print(greet.__name__)
   print(describe.__name__)
   ```
   - **Purpose**: Demonstrates decorated functions and metadata.
   - **Explanation**:
     - `greet("John")`: Outputs `HELLO JOHN`.
     - `describe("apple", "banana", "cherry")`: Outputs `Items: APPLE, BANANA, CHERRY` (uppercase due to internal decorator chain).
     - `greet.__name__, describe.__name__`: Outputs `greet`, `describe` (preserved by `functools.wraps`).

### Visual Description
When you run `python text_formatter.py` in the terminal, the output is:
```
Greet:
HELLO JOHN
Describe:
Items: APPLE, BANANA, CHERRY
Function Names:
greet
describe
```
Each section is clearly labeled, showing the formatted greeting, item list with prefix, and preserved function names.

### Common Mistakes and Fixes
1. **Forgetting `functools.wraps`**:
   - **Mistake**:
     ```python
     def uppercase(func):
         def wrapper(*args, **kwargs):
             return func(*args, **kwargs).upper()
         return wrapper
     ```
   - **Error**: `greet.__name__` returns `wrapper` instead of `greet`.
   - **Fix**: Add `@functools.wraps(func)`:
     ```python
     def uppercase(func):
         @functools.wraps(func)
         def wrapper(*args, **kwargs):
             return func(*args, **kwargs).upper()
         return wrapper
     ```
2. **Missing `*args, **kwargs` in Wrapper**:
   - **Mistake**:
     ```python
     def uppercase(func):
         def wrapper():
             return func().upper()
         return wrapper
     ```
   - **Error**: `TypeError` when `greet("John")` expects an argument.
   - **Fix**: Use `*args, **kwargs`:
     ```python
     def wrapper(*args, **kwargs):
         return func(*args, **kwargs).upper()
     ```
3. **Forgetting to Return Decorator in Factory**:
   - **Mistake**:
     ```python
     def add_prefix(s):
         def decorator(func):
             def wrapper(*args, **kwargs):
                 return f"{s}{func(*args, **kwargs)}"
             return wrapper
         # Missing return decorator
     ```
   - **Error**: `TypeError` (NoneType not callable).
   - **Fix**: Add `return decorator`:
     ```python
     def add_prefix(s):
         def decorator(func):
             def wrapper(*args, **kwargs):
                 return f"{s}{func(*args, **kwargs)}"
             return wrapper
         return decorator
     ```
4. **Incorrect Decorator Syntax**:
   - **Mistake**: `@add_prefix` instead of `@add_prefix("Items: ")`.
   - **Error**: `TypeError` (requires string argument).
   - **Fix**: Use correct syntax: `@add_prefix("Items: ")`.
5. **Wrong File Extension**:
   - **Mistake**: Saving as `text_formatter.txt`.
   - **Fix**: Save as `text_formatter.py` and run with `python text_formatter.py`.

### Validation Check
To confirm the program works:
1. Save the code in `text_formatter.py`.
2. Open a terminal, navigate to the file’s directory, and run `python text_formatter.py`.
3. Verify the output matches: `HELLO JOHN`, `Items: APPLE, BANANA, CHERRY`, and function names `greet`, `describe`.
4. Test with different inputs (e.g., `greet("Alice")` should output `HELLO ALICE`).
5. Test `describe()` with no arguments (should output `Items: `).
6. Add `print(greet.__doc__)` to confirm docstring preservation (`Returns a greeting for the given name.`).

### One-Line Takeaway
This program uses decorators with `functools.wraps` to format function outputs (uppercase, prefixed) while preserving metadata, demonstrating flexible text processing.