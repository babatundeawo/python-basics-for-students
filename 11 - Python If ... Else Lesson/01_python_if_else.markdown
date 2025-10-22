# Python If ... Else for Beginners

This tutorial covers Python's conditional statements, including `if`, `elif`, `else`, logical operators, nested `if`, `pass`, and the `match` statement. Below is a beginner-friendly teaching package based on the provided lesson note, designed to guide learners toward intermediate-level mastery with practical examples and exercises.

---

## Section 1 — Topical Explanations

### Learning Goals
- Understand how to use `if`, `elif`, and `else` for conditional logic.
- Learn logical operators (`and`, `or`, `not`) and comparison operators (`==`, `!=`, `<`, `<=`, `>`, `>=`).
- Explore shorthand `if` and ternary operators for concise conditions.
- Use nested `if` statements and the `pass` statement.
- Apply the `match` statement for pattern matching with default and combined cases.
- Emphasize proper indentation for defining code scope.

### Python Conditions and If Statements
Python supports comparison operators (`==`, `!=`, `<`, `<=`, `>`, `>=`) used in `if` statements to test conditions. An `if` statement executes a block of code if its condition is `True`.

**Example Code**:
```python
# If statement
a = 33
b = 200
if b > a:
    print("b is greater than a")  # Outputs: b is greater than a
```
- **Line-by-Line Explanation**:
  - `a = 33`: Assigns `33` to `a`. **Input**: `33`. **Output**: None. **Side Effects**: `a` is set.
  - `b = 200`: Assigns `200` to `b`. **Input**: `200`. **Output**: None. **Side Effects**: `b` is set.
  - `if b > a:`: Tests if `b` (200) is greater than `a` (33). **Input**: `b > a` (True). **Output**: None.
  - `print("b is greater than a")`: Executes if condition is `True`. **Output**: `b is greater than a`.
- **Visual Description**: Terminal shows `b is greater than a`.
- **Common Mistake**: Missing indentation.
  - **Error**: `IndentationError` if `print` is not indented, e.g., `if b > a: print("b is greater than a")`.
  - **Fix**: Indent with 4 spaces or one tab.
- **Validation Check**: Test with `a = 500`, `b = 200` to see no output (condition `False`).

### Indentation
Python uses indentation (whitespace) to define code blocks. Unlike other languages using curly brackets, Python requires consistent indentation (typically 4 spaces) for `if` blocks.

**Example Code** (Incorrect):
```python
a = 33
b = 200
if b > a:
print("b is greater than a")  # IndentationError
```
- **Explanation**: Missing indentation causes `IndentationError`.
- **Fix**: Indent the `print` statement:
  ```python
  if b > a:
      print("b is greater than a")  # Correct
  ```

### Elif
The `elif` keyword tests an additional condition if previous conditions are `False`.

**Example Code**:
```python
a = 33
b = 33
if b > a:
    print("b is greater than a")
elif a == b:
    print("a and b are equal")  # Outputs: a and b are equal
```
- **Explanation**:
  - `if b > a`: `False` (33 not > 33).
  - `elif a == b`: `True` (33 == 33). **Output**: `a and b are equal`.
- **Common Mistake**: Using `elif` without `if`.
  - **Error**: `SyntaxError`.
  - **Fix**: Always start with `if`.

### Else
The `else` keyword executes a block if all previous conditions are `False`.

**Example Code**:
```python
a = 200
b = 33
if b > a:
    print("b is greater than a")
elif a == b:
    print("a and b are equal")
else:
    print("a is greater than b")  # Outputs: a is greater than b
```
- **Explanation**:
  - `if b > a`: `False` (33 not > 200).
  - `elif a == b`: `False` (200 != 33).
  - `else`: Executes. **Output**: `a is greater than b`.
- **Common Mistake**: Using `else` with conditions, e.g., `else a < b:`.
  - **Error**: `SyntaxError`.
  - **Fix**: `else` takes no condition.

### Short Hand If and If ... Else (Ternary Operators)
A single-line `if` executes one statement. A ternary operator combines `if` and `else` in one line.

**Example Code**:
```python
a = 2
b = 330
if a > b: print("a is greater than b")  # No output
print("A") if a > b else print("B")  # Outputs: B
print("A") if a > b else print("=") if a == b else print("B")  # Outputs: B
```
- **Explanation**:
  - `if a > b: print("a is greater than b")`: `False`, no output.
  - `print("A") if a > b else print("B")`: Ternary operator; `a > b` is `False`, so prints `B`.
  - `print("A") if a > b else print("=") if a == b else print("B")`: Tests multiple conditions; prints `B` (2 != 330).
- **Common Mistake**: Overusing ternary operators, making code hard to read.
  - **Fix**: Use full `if` blocks for complex logic.

### Logical Operators (and, or, not)
Logical operators combine conditions: `and` (both `True`), `or` (at least one `True`), `not` (reverses result).

**Example Code**:
```python
a = 200
b = 33
c = 500
if a > b and c > a:
    print("Both conditions are True")  # Outputs: Both conditions are True
if a > b or a > c:
    print("At least one condition is True")  # Outputs: At least one condition is True
if not a > b:
    print("a is NOT greater than b")  # No output
```
- **Explanation**:
  - `a > b and c > a`: `True` (200 > 33 and 500 > 200). **Output**: `Both conditions are True`.
  - `a > b or a > c`: `True` (200 > 33). **Output**: `At least one condition is True`.
  - `not a > b`: `False` (not True). No output.
- **Common Mistake**: Using `&&` or `||` (from other languages).
  - **Error**: `SyntaxError`.
  - **Fix**: Use `and` and `or`.

### Nested If
`if` statements inside `if` statements allow layered conditions.

**Example Code**:
```python
x = 41
if x > 10:
    print("Above ten,")
    if x > 20:
        print("and also above 20!")  # Outputs: Above ten, and also above 20!
    else:
        print("but not above 20.")
```
- **Explanation**:
  - `if x > 10`: `True` (41 > 10). Prints `Above ten,`.
  - `if x > 20`: `True` (41 > 20). Prints `and also above 20!`.
- **Common Mistake**: Incorrect indentation in nested blocks.
  - **Fix**: Align nested `if` with 4 additional spaces.

### The pass Statement
`pass` is a placeholder for empty `if` blocks to avoid errors.

**Example Code**:
```python
a = 33
b = 200
if b > a:
    pass  # No error, no output
```
- **Explanation**: `pass` does nothing but prevents `SyntaxError`.
- **Common Mistake**: Leaving `if` empty, e.g., `if b > a:`.
  - **Error**: `SyntaxError`.
  - **Fix**: Use `pass`.

### The match Statement
The `match` statement (Python 3.10+) selects a code block based on an expression’s value, with support for default (`_`) and combined cases (`|`).

**Example Code**:
```python
day = 4
match day:
    case 1:
        print("Monday")
    case 2:
        print("Tuesday")
    case 3:
        print("Wednesday")
    case 4:
        print("Thursday")  # Outputs: Thursday
    case 5:
        print("Friday")
    case 6 | 7:
        print("Weekend")
    case _:
        print("Invalid day")
```
- **Explanation**:
  - `match day`: Evaluates `day` (4).
  - `case 4`: Matches, prints `Thursday`.
  - `case 6 | 7`: Combines values (weekend).
  - `case _`: Default case (not executed).
- **Common Mistake**: Placing `_` before other cases.
  - **Error**: Matches too early, skipping other cases.
  - **Fix**: Place `_` last.

**Match with If Guards**:
```python
month = 5
day = 4
match day:
    case 1 | 2 | 3 | 4 | 5 if month == 4:
        print("A weekday in April")
    case 1 | 2 | 3 | 4 | 5 if month == 5:
        print("A weekday in May")  # Outputs: A weekday in May
    case _:
        print("No match")
```
- **Explanation**: `if month == 5` ensures `case 1 | 2 | 3 | 4 | 5` only matches for May. **Output**: `A weekday in May`.

**One-Line Takeaway**: Python’s `if`, `elif`, `else`, and `match` statements, combined with logical operators and proper indentation, enable flexible conditional logic.

---

## Section 2 — Class Exercise

### Exercise: Number Comparison Tool

**Objective**: Write a Python program that compares two numbers and uses conditional statements to describe their relationship.

**Step-by-Step Instructions**:
1. Create a file named `number_compare.py`.
2. Declare variables `a = 50` and `b = 75`.
3. Perform and print:
   - Use `if`, `elif`, `else` to check if `a` is greater than, equal to, or less than `b`.
   - Use a shorthand `if` to print `"Large"` if `a + b > 100`.
   - Use a ternary operator to print `"Big"` if `a * b > 1000`, else `"Small"`.
   - Use `and` to check if both `a` and `b` are positive.
   - Use a nested `if` to check if `a > 25` and `a > b`.
4. Add comments to explain each step.
5. Run with `python number_compare.py`.

**Hints**:
- Ensure proper indentation (4 spaces) for `if` blocks.
- Use f-strings for clear output.
- Test multiple conditions carefully to avoid logical errors.

**Checkpoint**:
- Verify output matches expected comparisons.
- Ensure nested `if` logic is correct.

**Example Output** (for `a = 50`, `b = 75`):
```
Number Comparison:
b is greater than a
Sum is Large
Product is Big
Both numbers are positive
a is above 25, but not greater than b
```

---

## Section 3 — Weekly Project

### Project: Day Planner

**Objective**: Create a Python program that uses `match` and `if` statements to plan activities based on the day and hour.

**Milestones**:
1. Create a file named `day_planner.py`.
2. Declare variables `day = 4` (Thursday) and `hour = 14` (2 PM).
3. Perform:
   - Use `match` to print the day name (1=Monday, ..., 7=Sunday).
   - Use `if`, `elif`, `else` to suggest an activity based on `hour`:
     - Before 12: `"Morning meeting"`.
     - 12–17: `"Work on tasks"`.
     - After 17: `"Evening relaxation"`.
   - Use a nested `if` to check if it’s a weekday (1–5) and `hour < 16`, suggesting `"Focus time"`.
   - Use `match` with `|` to categorize `day` as `"Weekday"` (1–5) or `"Weekend"` (6–7).
   - Use `_` as a default case to handle invalid days.
   - Validate inputs (e.g., `1 <= day <= 7`, `0 <= hour <= 23`) with `if` and print `"Invalid input"` if invalid.
4. Print results with f-strings and comments.
5. Run with `python day_planner.py`.

**Deliverables**:
- A working `day_planner.py` file.
- Output showing day name, activity, and validations.

**Research Prompts**:
- How does Python’s `match` statement compare to `if` statements in terms of readability and performance?
- Why is indentation critical in Python, and how does it differ from other languages?

**Assessment Criteria**:
- Code runs without errors.
- `match` and `if` statements produce correct outputs.
- Input validation works.
- Output is clear and commented.
- Nested `if` and `match` with `|` are used correctly.

**Extension Idea**:
- Add a ternary operator to print `"Early"` or `"Late"` based on `hour < 12`.
- Use a loop to suggest activities for multiple hours.

**Example Output** (for `day = 4`, `hour = 14`):
```
Day Planner:
Day: Thursday
Activity: Work on tasks
Focus time (weekday and before 4 PM)
Category: Weekday
Inputs are valid
```

---

## Completion Checklist
- [ ] Understood `if`, `elif`, `else`, and comparison operators.
- [ ] Used logical operators (`and`, `or`, `not`) and shorthand `if`.
- [ ] Applied nested `if` and `pass` statements.
- [ ] Used `match` with default (`_`) and combined cases (`|`).
- [ ] Ensured proper indentation in all code blocks.
- [ ] Completed the class exercise and verified the output.
- [ ] Started the weekly project and planned the day planner.
- [ ] Fixed at least one common mistake (e.g., incorrect indentation).