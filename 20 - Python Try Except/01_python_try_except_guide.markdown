# Python Try Except: Beginner-Friendly Teaching Package

This teaching package transforms the provided lesson note on Python's `try-except` mechanism into a structured, beginner-friendly guide. It covers exception handling, including `try`, `except`, `else`, and `finally` blocks, as well as raising custom exceptions. The goal is to make these concepts accessible while guiding learners toward practical mastery through hands-on exercises and a project.

---

## Section 1 — Topical Explanations

### Learning Goals
By the end of this section, you’ll understand:
- How to use `try`, `except`, `else`, and `finally` blocks for exception handling.
- How to handle specific exceptions like `NameError` and `TypeError`.
- How to raise custom exceptions using the `raise` keyword.
- Practical applications, such as resource cleanup and error management.

### What is Exception Handling?
An **exception** is an error that occurs during program execution, causing Python to stop and display an error message. The `try-except` mechanism allows you to handle these errors gracefully, preventing crashes and providing meaningful feedback. Think of it like a safety net: the `try` block tests risky code, and the `except` block catches and handles errors.

### Basic Try-Except
The `try` block contains code that might raise an error, and the `except` block handles it.

**Example Code**:
```python
try:
    print(x)
except:
    print("An exception occurred")
```

**Line-by-Line Explanation**:
- `try:`: Starts the block where you test code for errors.
- `print(x)`: Attempts to print variable `x`, which is undefined, raising a `NameError`.
- `except:`: Catches any exception raised in the `try` block.
- `print("An exception occurred")`: Outputs a message when an error occurs.

**Expected Output**:
```
An exception occurred
```

**Visual Description**: Instead of crashing with a `NameError: name 'x' is not defined`, the program prints a user-friendly message and continues running.

**Common Mistake**:
- Using a bare `except` (without specifying an exception type) catches all errors, which can hide unexpected issues.
- **Fix**: Specify exception types (e.g., `except NameError`) when possible to handle only expected errors.

**Validation Check**: Define `x = 5` before the `try` block and verify no exception occurs (nothing prints from `except`).

### Handling Multiple Exceptions
You can handle specific exceptions by naming them in `except` blocks.

**Example Code**:
```python
try:
    print(x)
except NameError:
    print("Variable x is not defined")
except:
    print("Something else went wrong")
```

**Line-by-Line Explanation**:
- `try:`: Tests the code for errors.
- `print(x)`: Attempts to print undefined `x`, raising a `NameError`.
- `except NameError:`: Catches only `NameError` exceptions and prints a specific message.
- `except:`: Catches any other exceptions not handled by `NameError`.
- **Note**: The `except` blocks are checked in order, so specific exceptions must come before general ones.

**Expected Output**:
```
Variable x is not defined
```

**Visual Description**: The program identifies the specific error (`NameError`) and prints the corresponding message, ignoring the general `except` block.

**Common Mistake**:
- Placing the general `except` before specific ones, which prevents specific handlers from running.
- **Fix**: Always put specific `except` blocks (e.g., `except NameError`) before a general `except`.

**Validation Check**: Try raising a different error, like `1 / 0` (raises `ZeroDivisionError`), and confirm the general `except` block catches it.

### Using `else`
The `else` block runs if no exceptions occur in the `try` block.

**Example Code**:
```python
try:
    print("Hello")
except:
    print("Something went wrong")
else:
    print("Nothing went wrong")
```

**Line-by-Line Explanation**:
- `try:`: Tests the code.
- `print("Hello")`: Prints a string, which doesn’t raise an error.
- `except:`: Would catch any errors (not triggered here).
- `else:`: Runs only if no exceptions occur, printing a success message.

**Expected Output**:
```
Hello
Nothing went wrong
```

**Visual Description**: The `try` block executes successfully, so both the `try` block’s output and the `else` block’s message are printed.

**Common Mistake**:
- Putting code in the `else` block that should be in the `try` block, risking uncaught errors.
- **Fix**: Only put code in `else` that depends on the `try` block succeeding.

**Validation Check**: Add an error in the `try` block (e.g., `print(x)`) and confirm the `else` block doesn’t run.

### Using `finally`
The `finally` block runs regardless of whether an exception occurs, useful for cleanup tasks.

**Example Code**:
```python
try:
    print(x)
except:
    print("Something went wrong")
finally:
    print("The 'try except' is finished")
```

**Line-by-Line Explanation**:
- `try:`: Tests the code.
- `print(x)`: Raises a `NameError` since `x` is undefined.
- `except:`: Catches the error and prints a message.
- `finally:`: Always runs, printing a completion message.

**Expected Output**:
```
Something went wrong
The 'try except' is finished
```

**Visual Description**: Even though an error occurs, the `finally` block ensures the final message is printed, signaling the end of the operation.

**Common Mistake**:
- Forgetting that `finally` runs even if the program crashes later, potentially hiding cleanup issues.
- **Fix**: Use `finally` only for essential cleanup (e.g., closing files).

**Validation Check**: Define `x = 5` and confirm both the `try` and `finally` blocks run.

### Practical Example: File Handling
The `finally` block is often used to clean up resources, like closing files.

**Example Code**:
```python
try:
    f = open("demofile.txt")
    try:
        f.write("Lorum Ipsum")
    except:
        print("Something went wrong when writing to the file")
    finally:
        f.close()
except:
    print("Something went wrong when opening the file")
```

**Line-by-Line Explanation**:
- `try:`: Outer block tries to open a file.
- `f = open("demofile.txt")`: Attempts to open a file (may raise `FileNotFoundError` or `PermissionError`).
- Inner `try:`: Attempts to write to the file (may raise `PermissionError`).
- Inner `except:`: Catches write errors.
- Inner `finally:`: Ensures the file is closed, even if writing fails.
- Outer `except:`: Catches errors from opening the file.

**Expected Output** (if file is not writable):
```
Something went wrong when writing to the file
```

**Visual Description**: If the file opens but writing fails, the `except` block catches the error, and `finally` ensures the file is closed, preventing resource leaks.

**Common Mistake**:
- Not closing files in `finally`, leaving them open and causing issues.
- **Fix**: Always close resources in `finally` or use a `with` statement (e.g., `with open("demofile.txt") as f:`).

**Validation Check**: Create a `demofile.txt`, make it read-only, and confirm the write error is caught while the file is closed.

### Raising Exceptions
You can raise exceptions manually using the `raise` keyword to enforce conditions.

**Example Code**:
```python
x = -1
if x < 0:
    raise Exception("Sorry, no numbers below zero")
```

**Line-by-Line Explanation**:
- `x = -1`: Defines a variable.
- `if x < 0:`: Checks a condition.
- `raise Exception("Sorry, no numbers below zero")`: Raises a generic `Exception` with a custom message, stopping the program.

**Expected Output**:
```
Traceback (most recent call last):
  File "...", line 2, in <module>
    raise Exception("Sorry, no numbers below zero")
Exception: Sorry, no numbers below zero
```

**Visual Description**: The program stops and displays the custom error message when `x` is negative.

**Common Mistake**:
- Raising a generic `Exception` instead of a specific type, making it harder to handle.
- **Fix**: Use specific exceptions like `ValueError` or `TypeError` when appropriate.

### Raising Specific Exceptions
You can specify the type of exception to raise.

**Example Code**:
```python
x = "hello"
if not type(x) is int:
    raise TypeError("Only integers are allowed")
```

**Line-by-Line Explanation**:
- `x = "hello"`: Defines a non-integer variable.
- `if not type(x) is int:`: Checks if `x` is not an integer.
- `raise TypeError("Only integers are allowed")`: Raises a `TypeError` with a custom message.

**Expected Output**:
```
Traceback (most recent call last):
  File "...", line 2, in <module>
    raise TypeError("Only integers are allowed")
TypeError: Only integers are allowed
```

**Visual Description**: The program halts with a `TypeError`, clearly indicating the type mismatch.

**Common Mistake**:
- Using `raise` without catching it elsewhere, causing the program to crash.
- **Fix**: Wrap `raise` statements in a `try-except` block if you want to handle them.

**Validation Check**: Change `x` to `5` and confirm no error is raised.

**One-Line Takeaway**: The `try-except` mechanism, with `else`, `finally`, and `raise`, allows you to handle errors gracefully and enforce conditions in Python.

---

## Section 2 — Class Exercise

### Objectives
- Practice using `try`, `except`, `else`, and `finally` to handle errors.
- Raise custom exceptions based on conditions.
- Apply exception handling in a real-world scenario.

### Step-by-Step Instructions
1. **Handle Division Error**:
   - Write a script that prompts the user for two numbers and divides them.
   - Use `try-except` to handle `ZeroDivisionError` and print a message if the user tries to divide by zero.
   - Use `else` to print the result if division succeeds.
2. **Validate Input Type**:
   - Modify the script to check if inputs are numeric using `try-except` for `ValueError`.
   - Raise a `TypeError` if non-numeric input is provided.
3. **Add Cleanup**:
   - Use `finally` to print a message confirming the operation is complete, regardless of success or failure.

### Hints
- Use `input()` to get user input and `float()` to convert to numbers.
- Catch `ValueError` for non-numeric inputs and `ZeroDivisionError` for division by zero.
- Use `raise TypeError` to enforce numeric inputs.

### Checkpoints
- After step 1, test with inputs `10` and `2` (should output `5.0`) and `10` and `0` (should catch `ZeroDivisionError`).
- After step 2, test with `"abc"` and confirm a `TypeError` is raised.
- After step 3, verify the `finally` message appears in all cases.

---

## Section 3 — Weekly Project

### Overview
Create a **File Reader Tool** that reads a user-specified text file, counts its lines, and handles errors gracefully. The tool should use `try-except`, `else`, `finally`, and `raise` to manage file operations and validate inputs.

### Milestones
1. **File Input**:
   - Prompt the user for a file name (e.g., `data.txt`).
   - Validate the input is not empty; raise a `ValueError` if it is.
2. **File Reading**:
   - Use `try-except` to handle `FileNotFoundError` and `PermissionError` when opening the file.
   - Count and print the number of lines in the file if successful.
3. **Cleanup**:
   - Use `finally` to ensure the file is closed.
   - Print a completion message.

### Deliverables
- A Python script that:
  - Takes a file name as input.
  - Validates the input and reads the file.
  - Handles errors with specific messages.
  - Ensures cleanup with `finally`.
- Comments explaining the code.

### Research Prompts
- What other file-related exceptions might occur (e.g., `IOError`)?
- How does the `with` statement simplify file handling compared to `try-finally`?
- How can you check if a file exists before opening it?

### Assessment Criteria
- **Correctness**: The script reads files, counts lines, and handles errors correctly.
- **Clarity**: Code is commented, and error messages are user-friendly.
- **Completeness**: The script validates input, handles multiple exceptions, and ensures cleanup.

### Extension Ideas
- Add a feature to count words in the file.
- Allow the user to specify multiple files in a loop until they type "quit".
- Check if the file is a text file before reading (e.g., reject `.exe` files).

**Sample Approach** (not a full solution):
- Use `try: f = open(filename)` to open the file.
- Use `except FileNotFoundError` and `except PermissionError` for specific errors.
- Use `f.readlines()` to count lines and `finally: f.close()` for cleanup.

---

## Completion Checklist
- [ ] Understand `try`, `except`, `else`, `finally`, and `raise` with their purposes.
- [ ] Run the example codes and verify outputs (e.g., error messages, successful execution).
- [ ] Complete the class exercise, confirming error handling for division and input validation.
- [ ] Start the weekly project by writing a script to read a file and count lines.
- [ ] Avoid common mistakes like bare `except` or forgetting `finally` for cleanup.

**Common Pitfalls**:
- Using bare `except` instead of specific exceptions, masking unexpected errors.
- Not closing files in `finally`, causing resource leaks.
- Raising generic `Exception` instead of specific types like `ValueError`.

**One-Line Takeaway**: Python’s `try-except`, `else`, `finally`, and `raise` provide a robust way to handle errors, clean up resources, and enforce conditions in your programs.