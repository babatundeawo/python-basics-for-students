# Python Data Types for Beginners

This tutorial covers Python’s built-in data types, how to check and set them, type casting, and booleans. Below is a beginner-friendly teaching package designed to guide learners toward intermediate-level mastery with practical examples and exercises.

---

## Section 1 — Topical Explanations

### Learning Goals
- Understand Python’s built-in data types (e.g., `str`, `int`, `float`, `list`, `bool`).
- Learn how to check data types using `type()` and `isinstance()`.
- Master setting specific data types using constructor functions (e.g., `int()`, `str()`).
- Explore type casting to convert between data types.
- Understand booleans, how they’re evaluated, and their use in conditionals and functions.

### Built-in Data Types
Python variables can store different types of data, each suited for specific tasks. The main categories are:
- **Text**: `str` (e.g., `"Hello World"`).
- **Numeric**: `int` (e.g., `20`), `float` (e.g., `20.5`), `complex` (e.g., `1j`).
- **Sequence**: `list` (e.g., `["apple", "banana"]`), `tuple` (e.g., `("apple", "banana")`), `range` (e.g., `range(6)`).
- **Mapping**: `dict` (e.g., `{"name": "John", "age": 36}`).
- **Set**: `set` (e.g., `{"apple", "banana"}`), `frozenset` (immutable set).
- **Boolean**: `bool` (e.g., `True`, `False`).
- **Binary**: `bytes` (e.g., `b"Hello"`), `bytearray`, `memoryview`.
- **None**: `NoneType` (e.g., `None`).

Think of data types like different types of containers: a `str` is like a labeled box for text, an `int` for whole numbers, and a `list` for a collection of items.

### Getting the Data Type
Use the `type()` function to check a variable’s data type.

**Example Code**:
```python
x = 5  # Integer
print(type(x))  # Outputs: <class 'int'>
y = "Hello World"  # String
print(type(y))  # Outputs: <class 'str'>
```
- **Line-by-Line Explanation**:
  - `x = 5`: Assigns integer `5` to `x`. **Input**: `5`. **Output**: None. **Side Effects**: `x` holds `5`.
  - `print(type(x))`: Displays the type of `x` (`<class 'int'>`). **Input**: `x`. **Output**: `<class 'int'>`.
  - `y = "Hello World"`: Assigns string `"Hello World"` to `y`.
  - `print(type(y))`: Displays `<class 'str'>`.
- **Visual Description**: Running this code shows `<class 'int'>` and `<class 'str'>` on separate lines in the terminal.
- **Common Mistake**: Forgetting parentheses in `type()`.
  - **Error**: `NameError: name 'type' is not defined`.
  - **Fix**: Use `type(x)`, not `type x`.
- **Validation Check**: Add `print(type(x))` after assigning `x`. If it shows the expected type, it’s correct.

### Setting the Data Type
Python sets a variable’s type when a value is assigned. You can explicitly set types using constructor functions.

**Example Code**:
```python
x = str("Hello World")  # String: 'Hello World'
y = int(20)  # Integer: 20
z = float(20.5)  # Float: 20.5
w = list(("apple", "banana", "cherry"))  # List: ['apple', 'banana', 'cherry']
print(x, type(x))  # Outputs: Hello World <class 'str'>
print(y, type(y))  # Outputs: 20 <class 'int'>
print(z, type(z))  # Outputs: 20.5 <class 'float'>
print(w, type(w))  # Outputs: ['apple', 'banana', 'cherry'] <class 'list'>
```
- **Line-by-Line Explanation**:
  - `x = str("Hello World")`: Creates a string. **Input**: `"Hello World"`. **Output**: None. **Side Effects**: `x` holds `"Hello World"`.
  - `y = int(20)`: Creates an integer. **Input**: `20`. **Output**: None. **Side Effects**: `y` holds `20`.
  - `z = float(20.5)`: Creates a float. **Input**: `20.5`. **Output**: None. **Side Effects**: `z` holds `20.5`.
  - `w = list(("apple", "banana", "cherry"))`: Converts a tuple to a list. **Input**: `("apple", "banana", "cherry")`. **Output**: None. **Side Effects**: `w` holds `["apple", "banana", "cherry"]`.
  - `print(x, type(x))`: Outputs the value and type of each variable.
- **Visual Description**: Terminal shows each value followed by its type, e.g., `Hello World <class 'str'>`.
- **Common Mistake**: Using a constructor with an incompatible value (e.g., `int("hello")`).
  - **Error**: `ValueError: invalid literal for int()`.
  - **Fix**: Ensure the input is valid (e.g., `int("123")`).
- **Validation Check**: Print the type of each variable to confirm it matches the constructor used.

### Type Casting
Casting converts a value from one type to another using `int()`, `float()`, or `str()`.

**Example Code**:
```python
x = int(2.8)  # Float to int: removes decimals
y = float("3")  # String to float
z = str(3.0)  # Float to string
print(x, type(x))  # Outputs: 2 <class 'int'>
print(y, type(y))  # Outputs: 3.0 <class 'float'>
print(z, type(z))  # Outputs: 3.0 <class 'str'>
```
- **Line-by-Line Explanation**:
  - `x = int(2.8)`: Converts float `2.8` to integer `2` (truncates decimals). **Input**: `2.8`. **Output**: None. **Side Effects**: `x` holds `2`.
  - `y = float("3")`: Converts string `"3"` to float `3.0`. **Input**: `"3"`. **Output**: None. **Side Effects**: `y` holds `3.0`.
  - `z = str(3.0)`: Converts float `3.0` to string `"3.0"`. **Input**: `3.0`. **Output**: None. **Side Effects**: `z` holds `"3.0"`.
  - `print(x, type(x))`: Outputs value and type for each variable.
- **Visual Description**: Terminal shows `2 <class 'int'>`, `3.0 <class 'float'>`, `3.0 <class 'str'>` on separate lines.
- **Common Mistake**: Casting a non-numeric string to a number (e.g., `float("abc")`).
  - **Error**: `ValueError`.
  - **Fix**: Use a numeric string (e.g., `float("3.14")`).
- **Validation Check**: Use `print(type(x))` after casting to verify the new type.

### Booleans
Booleans represent `True` or `False`, often resulting from comparisons or evaluations.

**Example Code (Comparisons)**:
```python
print(10 > 9)  # Outputs: True
print(10 == 9)  # Outputs: False
print(10 < 9)  # Outputs: False
```
- **Explanation**:
  - `10 > 9`: Evaluates to `True` because 10 is greater than 9.
  - `10 == 9`: Evaluates to `False` (not equal).
  - `10 < 9`: Evaluates to `False` (not less than).
- **Visual Description**: Terminal shows `True`, `False`, `False` on separate lines.

**Example Code (Booleans in Conditionals)**:
```python
a = 200
b = 33
if b > a:
    print("b is greater than a")  # Skipped
else:
    print("b is not greater than a")  # Outputs: b is not greater than a
```
- **Explanation**:
  - `if b > a`: Checks if `33 > 200` (`False`), so the `else` block runs.
  - **Output**: `b is not greater than a`.
- **Common Mistake**: Forgetting the colon `:` after the `if` condition.
  - **Fix**: Ensure `if b > a:` includes the colon.

**Example Code (Evaluating with `bool()`)**:
```python
print(bool("Hello"))  # Outputs: True
print(bool(0))  # Outputs: False
print(bool([]))  # Outputs: False
```
- **Explanation**:
  - `bool("Hello")`: Non-empty strings are `True`.
  - `bool(0)`: Zero is `False`.
  - `bool([])`: Empty lists are `False`.
  - **Rules**: Most values are `True` (non-empty strings, non-zero numbers, non-empty collections). `False` values include `False`, `None`, `0`, `""`, `()`, `[]`, `{}`.
- **Common Mistake**: Assuming all non-zero numbers are `False`.
  - **Fix**: Remember only `0` is `False`; others (e.g., `-1`, `3.14`) are `True`.

**Example Code (Boolean Function)**:
```python
def myFunction():
    return True  # Returns boolean True

if myFunction():
    print("YES!")  # Outputs: YES!
else:
    print("NO!")
```
- **Explanation**:
  - `myFunction()`: Returns `True`.
  - `if myFunction()`: Executes the `True` block, printing `YES!`.

**Example Code (Using `isinstance()`)**:
```python
x = 200
print(isinstance(x, int))  # Outputs: True
```
- **Explanation**:
  - `isinstance(x, int)`: Checks if `x` is an integer. **Output**: `True`.
- **Common Mistake**: Using `isinstance(x, "int")`.
  - **Error**: `TypeError: isinstance() arg 2 must be a type`.
  - **Fix**: Use the type name without quotes, e.g., `isinstance(x, int)`.

**One-Line Takeaway**: Python’s built-in data types handle various data, with `type()` and `isinstance()` for checking, constructors for setting, and booleans for logical evaluations.

---

## Section 2 — Class Exercise

### Exercise: Data Type Explorer

**Objective**: Write a Python program that explores different data types, type casting, and boolean evaluation.

**Step-by-Step Instructions**:
1. Create a file named `types.py`.
2. Declare variables with different types:
   - `text` (string, e.g., `"Python"`).
   - `number` (cast string `"42"` to integer).
   - `decimal` (cast integer `10` to float).
   - `items` (list with three strings, e.g., `["pen", "book", "ruler"]`).
   - `flag` (boolean, evaluate `number > 40`).
3. Print each variable’s value and type using `type()`.
4. Use `isinstance()` to check if `number` is an integer.
5. Add comments to explain each variable.
6. Run the program with `python types.py`.

**Hints**:
- Use `int("42")` for casting to integer.
- Use commas in `print()` to combine values and types.
- Use `bool(number > 40)` for the boolean.

**Checkpoint**:
- Check if the output shows correct values and types.
- Verify `isinstance(number, int)` returns `True`.

**Example Output** (for `text = "Python"`, `number = "42"`, `decimal = 10`, `items = ["pen", "book", "ruler"]`, `flag = number > 40`):
```
Text: Python , Type: <class 'str'>
Number: 42 , Type: <class 'int'>
Decimal: 10.0 , Type: <class 'float'>
Items: ['pen', 'book', 'ruler'] , Type: <class 'list'>
Flag: True , Type: <class 'bool'>
Is number an integer? True
```

---

## Section 3 — Weekly Project

### Project: Type-Based Profile Validator

**Objective**: Create a Python program that validates a user profile by checking data types and boolean conditions.

**Milestones**:
1. Create a file named `profile_validator.py`.
2. Declare variables:
   - `user_name` (string, e.g., `"Alice"`).
   - `user_age` (cast string `"25"` to integer).
   - `user_height` (cast integer `170` to float).
   - `skills` (list, e.g., `["coding", "design"]`).
   - `is_active` (boolean, check if `len(skills) > 0`).
3. Print each variable’s value and type using `type()`.
4. Use `isinstance()` to validate that `user_age` is an integer and `user_height` is a float.
5. If `is_active` is `True`, print: `Profile is active with [len(skills)] skills.`
6. Add comments to explain each section.

**Deliverables**:
- A working `profile_validator.py` file.
- Output showing variable values, types, and validation results.

**Research Prompts**:
- What types evaluate to `False` in a boolean context?
- How does `isinstance()` differ from `type()`?

**Assessment Criteria**:
- Code runs without errors.
- Variables are correctly typed using constructors.
- Output includes values, types, and validation results.
- Comments explain key steps.
- Boolean condition correctly evaluates `is_active`.

**Extension Idea**:
- Add a `dict` variable for user info (e.g., `{"role": "developer", "experience": 2}`) and check its type.
- Use a function to return a boolean based on whether `user_age >= 18`.

**Example Output**:
```
User Name: Alice , Type: <class 'str'>
User Age: 25 , Type: <class 'int'>
User Height: 170.0 , Type: <class 'float'>
Skills: ['coding', 'design'] , Type: <class 'list'>
Is Active: True , Type: <class 'bool'>
Is user_age an integer? True
Is user_height a float? True
Profile is active with 2 skills.
```

---

## Completion Checklist
- [ ] Understood Python’s built-in data types (str, int, float, list, bool, etc.).
- [ ] Used `type()` to check variable types.
- [ ] Set specific types using constructors (e.g., `int()`, `float()`, `list()`).
- [ ] Performed type casting and verified results.
- [ ] Evaluated booleans using comparisons, `bool()`, and `isinstance()`.
- [ ] Completed the class exercise and verified the output.
- [ ] Started the weekly project and planned the profile validator.
- [ ] Fixed at least one common mistake (e.g., invalid casting or missing colon).