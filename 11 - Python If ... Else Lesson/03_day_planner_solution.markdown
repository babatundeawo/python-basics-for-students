# Solution to Python Weekly Project: Day Planner

This document provides the solution to the Python weekly project from the Python If ... Else tutorial, where the task is to create a program that uses `match` and `if` statements to plan activities based on the day and hour. Below is the solution code, followed by a detailed explanation tailored for beginners.

---

## Solution Code

```python
# day_planner.py
# This program plans activities based on day and hour using match and if statements

"""
Program: Day Planner
Author: [Your Name]
Purpose: Demonstrates using match and if statements to plan activities based on day and hour
"""

# Declare variables
day = 4  # Thursday
hour = 14  # 2 PM

# Validate inputs
print("Day Planner:")
if not (1 <= day <= 7 and 0 <= hour <= 23):
    print("Invalid input")  # No output since inputs are valid
else:
    # Print day name using match
    match day:
        case 1:
            print("Day: Monday")
        case 2:
            print("Day: Tuesday")
        case 3:
            print("Day: Wednesday")
        case 4:
            print("Day: Thursday")  # Outputs: Day: Thursday
        case 5:
            print("Day: Friday")
        case 6:
            print("Day: Saturday")
        case 7:
            print("Day: Sunday")
        case _:
            print("Invalid day")  # Not reached due to validation

    # Suggest activity based on hour
    if hour < 12:
        print("Activity: Morning meeting")
    elif 12 <= hour <= 17:
        print("Activity: Work on tasks")  # Outputs: Activity: Work on tasks
    else:
        print("Activity: Evening relaxation")

    # Nested if for weekday and hour < 16
    if 1 <= day <= 5:
        if hour < 16:
            print("Focus time (weekday and before 4 PM)")  # Outputs: Focus time
        else:
            print("No focus time (after 4 PM)")

    # Categorize day using match with |
    match day:
        case 1 | 2 | 3 | 4 | 5:
            print("Category: Weekday")  # Outputs: Category: Weekday
        case 6 | 7:
            print("Category: Weekend")
        case _:
            print("Invalid day")  # Not reached due to validation

    print("Inputs are valid")
```

**Expected Output** (for `day = 4`, `hour = 14`):
```
Day Planner:
Day: Thursday
Activity: Work on tasks
Focus time (weekday and before 4 PM)
Category: Weekday
Inputs are valid
```

---

## Explanation

### Objective
The project requires creating a Python program (`day_planner.py`) that:
- Declares variables `day = 4` (Thursday) and `hour = 14` (2 PM).
- Performs:
  - Uses `match` to print the day name (1=Monday, ..., 7=Sunday).
  - Uses `if`, `elif`, `else` to suggest an activity based on `hour`:
    - Before 12: `"Morning meeting"`.
    - 12–17: `"Work on tasks"`.
    - After 17: `"Evening relaxation"`.
  - Uses a nested `if` to check if it’s a weekday (1–5) and `hour < 16`, suggesting `"Focus time"`.
  - Uses `match` with `|` to categorize `day` as `"Weekday"` (1–5) or `"Weekend"` (6–7).
  - Uses `_` as a default case to handle invalid days.
  - Validates inputs (`1 <= day <= 7`, `0 <= hour <= 23`) with `if` and prints `"Invalid input"` if invalid.
- Prints results with f-strings and comments.
- Runs correctly with `python day_planner.py`.

### Line-by-Line Breakdown
Let’s walk through the code to understand each part, its input, output, and purpose:

1. **File Creation**:
   - The code is saved in a file named `day_planner.py`. This ensures Python recognizes it as a Python script when you run `python day_planner.py`.

2. **Single-Line Comment**:
   ```python
   # day_planner.py
   # This program plans activities based on day and hour using match and if statements
   ```
   - **Purpose**: Describes the file and program purpose. Ignored by Python.
   - **Input**: None.
   - **Output**: None.
   - **Side Effects**: None.

3. **Multiline Comment**:
   ```python
   """
   Program: Day Planner
   Author: [Your Name]
   Purpose: Demonstrates using match and if statements to plan activities based on day and hour
   """
   ```
   - **Purpose**: Provides detailed documentation. Ignored by Python since it’s not assigned.
   - **Input**: None.
   - **Output**: None.
   - **Side Effects**: None.

4. **Variable Declaration**:
   ```python
   day = 4  # Thursday
   hour = 14  # 2 PM
   ```
   - **Purpose**: Assigns `4` to `day` (Thursday) and `14` to `hour` (2 PM). **Input**: `4`, `14`. **Output**: None. **Side Effects**: Sets `day` and `hour`.

5. **Validate Inputs**:
   ```python
   print("Day Planner:")
   if not (1 <= day <= 7 and 0 <= hour <= 23):
       print("Invalid input")
   else:
   ```
   - **Purpose**: Checks if `1 <= day <= 7` and `0 <= hour <= 23`. For `day = 4`, `hour = 14`, condition is `True`, so proceeds to `else`.
   - **Output**: `Day Planner:`.
   - **Side Effects**: Controls flow to `else` block.

6. **Print Day Name Using `match`**:
   ```python
   match day:
       case 1:
           print("Day: Monday")
       case 2:
           print("Day: Tuesday")
       case 3:
           print("Day: Wednesday")
       case 4:
           print("Day: Thursday")  # Outputs: Day: Thursday
       case 5:
           print("Day: Friday")
       case 6:
           print("Day: Saturday")
       case 7:
           print("Day: Sunday")
       case _:
           print("Invalid day")
   ```
   - **Purpose**: Uses `match` to print day name. Matches `day = 4` to `case 4`. **Output**: `Day: Thursday`.
   - **Side Effects**: Only printing.

7. **Suggest Activity Based on Hour**:
   ```python
   if hour < 12:
       print("Activity: Morning meeting")
   elif 12 <= hour <= 17:
       print("Activity: Work on tasks")  # Outputs: Activity: Work on tasks
   else:
       print("Activity: Evening relaxation")
   ```
   - **Purpose**: Suggests activity based on `hour`. Since `14` satisfies `12 <= hour <= 17`, prints `Activity: Work on tasks`. **Output**: `Activity: Work on tasks`.

8. **Nested `if` for Weekday and Hour**:
   ```python
   if 1 <= day <= 5:
       if hour < 16:
           print("Focus time (weekday and before 4 PM)")  # Outputs: Focus time
       else:
           print("No focus time (after 4 PM)")
   ```
   - **Purpose**: Checks if `day` is a weekday (1–5) and `hour < 16`. Since `day = 4` and `hour = 14 < 16`, prints `Focus time (weekday and before 4 PM)`. **Output**: `Focus time (weekday and before 4 PM)`.

9. **Categorize Day Using `match` with `|`**:
   ```python
   match day:
       case 1 | 2 | 3 | 4 | 5:
           print("Category: Weekday")  # Outputs: Category: Weekday
       case 6 | 7:
           print("Category: Weekend")
       case _:
           print("Invalid day")
   ```
   - **Purpose**: Categorizes `day`. Matches `day = 4` to `case 1 | 2 | 3 | 4 | 5`. **Output**: `Category: Weekday`.

10. **Confirm Valid Inputs**:
    ```python
    print("Inputs are valid")
    ```
    - **Purpose**: Prints confirmation since validation passed. **Output**: `Inputs are valid`.

### Visual Description
When you run `python day_planner.py` in the terminal, the output is:
```
Day Planner:
Day: Thursday
Activity: Work on tasks
Focus time (weekday and before 4 PM)
Category: Weekday
Inputs are valid
```
Each line shows the result of a conditional check or pattern match with descriptive labels, clearly indicating the day, activity, and category.

### Common Mistakes and Fixes
1. **Incorrect Indentation**:
   - **Mistake**:
     ```python
     if hour < 12:
     print("Activity: Morning meeting")  # IndentationError
     ```
   - **Error**: `IndentationError`.
   - **Fix**: Indent with 4 spaces:
     ```python
     if hour < 12:
         print("Activity: Morning meeting")
     ```
2. **Placing `_` Before Other Cases in `match`**:
   - **Mistake**:
     ```python
     match day:
         case _:
             print("Invalid day")
         case 4:
             print("Day: Thursday")  # Never reached
     ```
   - **Error**: `case 4` is unreachable.
   - **Fix**: Place `_` last.
3. **Invalid Logical Operator**:
   - **Mistake**:
     ```python
     if 1 <= day <= 5 && hour < 16:  # SyntaxError
     ```
   - **Error**: `SyntaxError`.
   - **Fix**: Use `and`:
     ```python
     if 1 <= day <= 5 and hour < 16:
     ```
4. **Missing Input Validation**:
   - **Mistake**: Omitting validation, allowing `day = 8` to reach `case _`.
   - **Fix**: Include validation:
     ```python
     if not (1 <= day <= 7 and 0 <= hour <= 23):
         print("Invalid input")
     ```
5. **Wrong File Extension**:
   - **Mistake**: Saving as `day_planner.txt`.
   - **Fix**: Save as `day_planner.py` and run with `python day_planner.py`.

### Validation Check
To confirm the program works:
1. Save the code in `day_planner.py`.
2. Open a terminal, navigate to the file’s directory, and run `python day_planner.py`.
3. Verify the output matches: `Day: Thursday`, `Activity: Work on tasks`, `Focus time (weekday and before 4 PM)`, `Category: Weekday`, `Inputs are valid`.
4. Test with different values (e.g., `day = 6`, `hour = 18`):
   - Expected output: `Day: Saturday`, `Activity: Evening relaxation`, `Category: Weekend`, `Inputs are valid` (no focus time message).
5. Test invalid input (e.g., `day = 8`):
   - Expected output: `Day Planner:`, `Invalid input`.
6. Add `print(type(day))` to confirm `day` is an integer (`<class 'int'>`).

### Extension Idea Implementation
For learners interested in the extension ideas:
- **Add Ternary Operator for Early/Late**:
  ```python
  print("Early") if hour < 12 else print("Late")  # Add after activity
  ```
  - For `hour = 14`, outputs `Late`.
- **Loop for Multiple Hours**:
  ```python
  for h in [8, 14, 18]:
      print(f"Hour {h}: {'Morning meeting' if h < 12 else 'Work on tasks' if h <= 17 else 'Evening relaxation'}")
  ```
  - Add at end. Outputs: `Hour 8: Morning meeting`, `Hour 14: Work on tasks`, `Hour 18: Evening relaxation`.

### Research Prompts Answered
- **How does Python’s `match` statement compare to `if` statements in terms of readability and performance?**
  - **Readability**: `match` is more concise for pattern matching (e.g., day names), reducing nested `if` statements. It’s clearer for multiple discrete values with `|`. `if` is better for complex conditions (e.g., ranges like `hour < 12`).
  - **Performance**: `match` can be slightly faster for direct value matching due to optimized lookup, but the difference is minimal for small cases. `if` is more flexible for dynamic conditions.
- **Why is indentation critical in Python, and how does it differ from other languages?**
  - **Critical in Python**: Python uses indentation to define code blocks, unlike languages like C or Java that use curly braces `{}`. Incorrect indentation causes `IndentationError` or logical errors.
  - **Difference**: Other languages allow flexible whitespace, relying on explicit delimiters. Python’s approach enforces readability but requires consistent indentation (4 spaces recommended).

### One-Line Takeaway
This program uses `match` for day names and categorization, `if`/`elif`/`else` for activities, nested `if` for focus time, and input validation to plan activities based on day and hour.