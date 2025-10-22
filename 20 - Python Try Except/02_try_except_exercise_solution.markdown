# Python Try Except Class Exercise: Solutions and Explanations

This Markdown file provides the solutions to the class exercise from the Python Try Except teaching package, along with detailed explanations. The exercise focuses on using `try`, `except`, `else`, and `finally` blocks to handle errors in a division operation, validate input types, and ensure cleanup. Each solution includes step-by-step instructions, expected outputs, visual descriptions, common mistakes, and validation checks, adhering to the beginner-friendly instructional framework.

---

## Exercise Objectives
- Practice using `try`, `except`, `else`, and `finally` to handle errors.
- Raise custom exceptions based on conditions.
- Apply exception handling in a real-world scenario (division of user inputs).

## Exercise Tasks
1. **Handle Division Error**:
   - Write a script that prompts the user for two numbers and divides them.
   - Use `try-except` to handle `ZeroDivisionError` and print a message if the user tries to divide by zero.
   - Use `else` to print the result if division succeeds.
2. **Validate Input Type**:
   - Modify the script to check if inputs are numeric using `try-except` for `ValueError`.
   - Raise a `TypeError` if non-numeric input is provided.
3. **Add Cleanup**:
   - Use `finally` to print a message confirming the operation is complete, regardless of success or failure.

---

## Solution

Below is the complete Python script that addresses all tasks.

```python
try:
    # Get user input for two numbers
    num1 = input("Enter the first number: ")
    num2 = input("Enter the second number: ")

    # Validate input type by attempting to convert to float
    try:
        num1 = float(num1)
        num2 = float(num2)
    except ValueError:
        raise TypeError("Only numeric inputs are allowed")

    # Perform division
    result = num1 / num2

except ZeroDivisionError:
    print("Error: Cannot divide by zero")
except TypeError as e:
    print(f"Error: {e}")
except:
    print("An unexpected error occurred")
else:
    print(f"The result of {num1} divided by {num2} is: {result}")
finally:
    print("Division operation completed")
```

---

## Explanations

### Task 1: Handle Division Error
**Objective**: Prompt for two numbers, divide them, handle `ZeroDivisionError`, and use `else` for successful division.

**Relevant Code**:
```python
try:
    num1 = input("Enter the first number: ")
    num2 = input("Enter the second number: ")
    num1 = float(num1)  # Simplified for Task 1
    num2 = float(num2)
    result = num1 / num2
except ZeroDivisionError:
    print("Error: Cannot divide by zero")
else:
    print(f"The result of {num1} divided by {num2} is: {result}")
```

**Line-by-Line Explanation**:
- `try:`: Starts the block to test for errors.
- `num1 = input("Enter the first number: ")`: Prompts for the first number.
- `num2 = input("Enter the second number: ")`: Prompts for the second number.
- `num1 = float(num1)`: Converts the first input to a float (assumes numeric for Task 1).
- `num2 = float(num2)`: Converts the second input to a float.
- `result = num1 / num2`: Performs division, which may raise `ZeroDivisionError` if `num2` is 0.
- `except ZeroDivisionError:`: Catches division by zero and prints an error message.
- `else:`: Runs if no exception occurs, printing the division result.

**Expected Output** (for inputs `10` and `2`):
```
Enter the first number: 10
Enter the second number: 2
The result of 10.0 divided by 2.0 is: 5.0
```

**Expected Output** (for inputs `10` and `0`):
```
Enter the first number: 10
Enter the second number: 0
Error: Cannot divide by zero
```

**Visual Description**: The script prompts for two numbers and either displays the division result (e.g., `5.0`) or an error message if the second number is zero.

**Common Mistake**:
- Not handling `ZeroDivisionError` specifically, causing the program to crash.
- **Fix**: Always include an `except ZeroDivisionError` for division operations.

**Validation Check**: Test with `10` and `2` (output: `5.0`) and `10` and `0` (output: error message).

### Task 2: Validate Input Type
**Objective**: Check if inputs are numeric, raising a `TypeError` for non-numeric inputs using `try-except` for `ValueError`.

**Relevant Code** (integrated in the full script):
```python
try:
    num1 = input("Enter the first number: ")
    num2 = input("Enter the second number: ")
    try:
        num1 = float(num1)
        num2 = float(num2)
    except ValueError:
        raise TypeError("Only numeric inputs are allowed")
except TypeError as e:
    print(f"Error: {e}")
```

**Line-by-Line Explanation**:
- Outer `try:`: Wraps the entire operation to catch errors.
- `num1 = input(...)` and `num2 = input(...)`: Get user inputs as strings.
- Inner `try:`: Attempts to convert inputs to floats.
- `num1 = float(num1)`: Converts the first input; raises `ValueError` if non-numeric.
- `num2 = float(num2)`: Converts the second input.
- `except ValueError:`: Catches invalid numeric conversions.
- `raise TypeError("Only numeric inputs are allowed")`: Raises a `TypeError` for clarity.
- Outer `except TypeError as e:`: Catches the raised `TypeError` and prints its message.

**Expected Output** (for inputs `"abc"` and `2`):
```
Enter the first number: abc
Enter the second number: 2
Error: Only numeric inputs are allowed
```

**Visual Description**: If the user enters a non-numeric value (e.g., `"abc"`), the script raises and catches a `TypeError`, displaying a clear error message.

**Common Mistake**:
- Not catching `ValueError` during type conversion, causing the program to crash.
- **Fix**: Use a nested `try-except` to handle `ValueError` and raise a more specific `TypeError`.

**Validation Check**: Test with `"abc"` and `2` (should raise `TypeError`) and `10` and `2` (should proceed to division).

### Task 3: Add Cleanup
**Objective**: Use `finally` to print a completion message in all cases.

**Relevant Code** (from the full script):
```python
finally:
    print("Division operation completed")
```

**Line-by-Line Explanation**:
- `finally:`: Runs regardless of whether an exception occurs.
- `print("Division operation completed")`: Outputs a message to signal the end of the operation.

**Expected Output** (combined with Task 1 and 2 scenarios):
- For `10` and `2`:
  ```
  Enter the first number: 10
  Enter the second number: 2
  The result of 10.0 divided by 2.0 is: 5.0
  Division operation completed
  ```
- For `10` and `0`:
  ```
  Enter the first number: 10
  Enter the second number: 0
  Error: Cannot divide by zero
  Division operation completed
  ```
- For `"abc"` and `2`:
  ```
  Enter the first number: abc
  Enter the second number: 2
  Error: Only numeric inputs are allowed
  Division operation completed
  ```

**Visual Description**: The `finally` block ensures the completion message appears after every execution, whether the division succeeds, fails due to zero division, or fails due to invalid input.

**Common Mistake**:
- Omitting `finally`, missing an opportunity to confirm operation completion.
- **Fix**: Always include `finally` for cleanup or status messages in critical operations.

**Validation Check**: Confirm the `finally` message appears in all test cases (successful division, zero division, invalid input).

### General Error Handling
The script includes a general `except` block:
```python
except:
    print("An unexpected error occurred")
```
- **Purpose**: Catches any unhandled exceptions (e.g., unexpected issues like memory errors).
- **Why Include It**: Ensures the program doesn’t crash on unforeseen errors.

**Common Mistake**:
- Using a bare `except` as the only handler, masking specific errors.
- **Fix**: Place specific `except` blocks (e.g., `ZeroDivisionError`, `TypeError`) before the general `except`.

---

## Completion Checklist
- [ ] Ran the script with inputs `10` and `2`, verifying output `5.0` and `finally` message.
- [ ] Tested with `10` and `0`, confirming `ZeroDivisionError` is caught and `finally` message appears.
- [ ] Tested with `"abc"` and `2`, ensuring `TypeError` is raised and caught with `finally` message.
- [ ] Verified the `else` block runs only on successful division.
- [ ] Avoided bare `except` as the primary handler, using specific exceptions first.

**Common Pitfalls**:
- Forgetting to handle `ValueError` when converting inputs to floats.
- Placing the general `except` before specific `except` blocks, preventing them from running.
- Not including `finally` to confirm operation completion.

**One-Line Takeaway**: The script uses `try-except`, `else`, and `finally` to handle division errors, validate numeric inputs with `TypeError`, and ensure a completion message, making it robust and user-friendly.