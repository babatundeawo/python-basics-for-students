# Python Variables for Beginners

This tutorial expands on Python variables, covering their creation, naming conventions, types, multiple assignments, output methods, and global/local scope. Below is a beginner-friendly teaching package designed to guide learners toward intermediate-level mastery with practical examples and exercises.

---

## Section 1 — Topical Explanations

### Learning Goals
- Understand how to create and use variables in Python.
- Learn variable naming rules and conventions (e.g., camelCase, PascalCase, snake_case).
- Explore type casting and checking variable types with `type()`.
- Master assigning multiple values and unpacking collections.
- Learn how to output variables using `print()` with commas or `+`.
- Understand global and local variables and the `global` keyword.

### Creating Variables
Variables are containers for storing data, like numbers or text. In Python, you create a variable by assigning a value using `=`, without needing a special declaration.

**Example Code**:
```python
x = 5  # Assigns integer 5 to x
y = "John"  # Assigns string "John" to y
print(x)  # Outputs: 5
print(y)  # Outputs: John
```
- **Line-by-Line Explanation**:
  - `x = 5`: Creates variable `x` with the integer `5`. **Input**: `5`. **Output**: None (stores value). **Side Effects**: `x` holds `5`.
  - `y = "John"`: Creates variable `y` with the string `"John"`. **Input**: `"John"`. **Output**: None. **Side Effects**: `y` holds `"John"`.
  - `print(x)`: Displays `5`. **Input**: `x`. **Output**: `5`.
  - `print(y)`: Displays `John`. **Input**: `y`. **Output**: `John`.
- **Visual Description**: Running this code shows `5` and `John` on separate lines in the terminal.
- **Common Mistake**: Assuming a variable must be declared with a type (e.g., `int x = 5` like in other languages). Python creates variables on assignment.
  - **Fix**: Simply assign a value: `x = 5`.
- **Validation Check**: Add `print(x)` after `x = 5`. If it prints `5`, the variable is set correctly.

**Dynamic Typing**:
Variables can change type after being set:
```python
x = 4  # x is an integer
x = "Sally"  # x is now a string
print(x)  # Outputs: Sally
```
- **Explanation**: `x` starts as an integer (`4`), then becomes a string (`"Sally"`). Python dynamically updates the type. **Output**: `Sally`.
- **Common Mistake**: Expecting a type error when changing types. Python allows this flexibility.
  - **Fix**: Be aware that reassigning a variable changes its value and type.

### Casting
You can specify a variable’s type using casting functions like `str()`, `int()`, or `float()`.

**Example Code**:
```python
x = str(3)  # Converts 3 to string '3'
y = int(3)  # Converts 3 to integer 3
z = float(3)  # Converts 3 to float 3.0
print(x, y, z)  # Outputs: 3 3 3.0
print(type(x), type(y), type(z))  # Outputs: <class 'str'> <class 'int'> <class 'float'>
```
- **Line-by-Line Explanation**:
  - `x = str(3)`: Converts integer `3` to string `"3"`. **Input**: `3`. **Output**: None. **Side Effects**: `x` holds `"3"`.
  - `y = int(3)`: Ensures `3` is an integer. **Input**: `3`. **Output**: None. **Side Effects**: `y` holds `3`.
  - `z = float(3)`: Converts `3` to float `3.0`. **Input**: `3`. **Output**: None. **Side Effects**: `z` holds `3.0`.
  - `print(x, y, z)`: Outputs `3 3 3.0` (space-separated due to commas).
  - `print(type(x), type(y), type(z))`: Shows types: `str`, `int`, `float`.
- **Visual Description**: Terminal shows `3 3 3.0` on one line, then `<class 'str'> <class 'int'> <class 'float'>` on the next.
- **Common Mistake**: Trying to cast incompatible types (e.g., `int("hello")`).
  - **Error**: `ValueError: invalid literal for int()`.
  - **Fix**: Ensure the value can be converted (e.g., `int("123")` works).
- **Validation Check**: Use `print(type(x))` to confirm the type matches the casting function.

### Variable Naming Rules and Conventions
Variable names must follow these rules:
- Start with a letter or underscore (`_`).
- Contain only letters, numbers, and underscores (A-z, 0-9, `_`).
- Case-sensitive (e.g., `age` and `Age` are different).
- Cannot be Python keywords (e.g., `if`, `for`).

**Example Code**:
```python
myvar = "John"  # Valid: lowercase
my_var = "John"  # Valid: snake_case
_my_var = "John"  # Valid: starts with underscore
myVar = "John"  # Valid: camelCase
MYVAR = "John"  # Valid: uppercase
myvar2 = "John"  # Valid: includes number
# 2myvar = "John"  # Invalid: starts with number
# my-var = "John"  # Invalid: contains hyphen
# my var = "John"  # Invalid: contains space
```
- **Explanation**:
  - Valid names work and store `"John"`.
  - Invalid names (commented out) cause `SyntaxError`.
- **Naming Conventions**:
  - **Camel Case**: `myVariableName` (first word lowercase, others capitalized).
  - **Pascal Case**: `MyVariableName` (all words capitalized).
  - **Snake Case**: `my_variable_name` (words separated by underscores, preferred in Python).
- **Common Mistake**: Using invalid characters or starting with a number.
  - **Fix**: Use letters or underscores to start, and stick to alphanumeric characters or underscores.
- **Validation Check**: Create a variable like `my_var = 10` and print it. If it works, the name is valid.

### Assigning Multiple Values
Python allows assigning values to multiple variables in one line or unpacking collections.

**Example Code (Multiple Variables)**:
```python
x, y, z = "Orange", "Banana", "Cherry"  # Assigns three values to three variables
print(x, y, z)  # Outputs: Orange Banana Cherry
```
- **Explanation**:
  - `x, y, z = "Orange", "Banana", "Cherry"`: Assigns `"Orange"` to `x`, `"Banana"` to `y`, `"Cherry"` to `z`.
  - **Input**: The values `"Orange"`, `"Banana"`, `"Cherry"`.
  - **Output**: None (stores values).
  - **Side Effects**: `x`, `y`, `z` hold their respective values.
  - `print(x, y, z)`: Outputs `Orange Banana Cherry` (space-separated).
- **Common Mistake**: Mismatching the number of variables and values.
  - **Error**: `ValueError: too many values to unpack` (e.g., `x, y = 1, 2, 3`).
  - **Fix**: Ensure the number of variables equals the number of values.

**Example Code (One Value to Multiple Variables)**:
```python
x = y = z = "Orange"  # Assigns "Orange" to all three variables
print(x, y, z)  # Outputs: Orange Orange Orange
```
- **Explanation**: All variables (`x`, `y`, `z`) are assigned `"Orange"`.

**Example Code (Unpacking a List)**:
```python
fruits = ["apple", "banana", "cherry"]  # List of fruits
x, y, z = fruits  # Unpacks list into variables
print(x, y, z)  # Outputs: apple banana cherry
```
- **Explanation**:
  - `fruits = ["apple", "banana", "cherry"]`: Creates a list.
  - `x, y, z = fruits`: Unpacks the list into `x = "apple"`, `y = "banana"`, `z = "cherry"`.
  - **Common Mistake**: Unpacking with the wrong number of variables.
    - **Fix**: Match the number of variables to the list length.

### Outputting Variables
The `print()` function outputs variables, either with commas (for multiple variables) or `+` (for strings).

**Example Code**:
```python
x = "Python"
y = "is"
z = "awesome"
print(x, y, z)  # Outputs: Python is awesome
print(x + " " + y + " " + z)  # Outputs: Python is awesome
```
- **Explanation**:
  - `print(x, y, z)`: Commas separate variables, adding spaces automatically. **Output**: `Python is awesome`.
  - `print(x + " " + y + " " + z)`: Concatenates strings with explicit spaces. **Output**: Same as above.
- **Common Mistake**: Using `+` with strings and numbers.
  - **Error Example**:
    ```python
    x = 5
    y = "John"
    print(x + y)  # TypeError: unsupported operand type(s)
    ```
  - **Fix**: Use commas (`print(x, y)`) or convert numbers to strings (`print(str(x) + y)`).
- **Validation Check**: Use `print(x, y)` to ensure different types output correctly.

**Numbers with `+`**:
```python
x = 5
y = 10
print(x + y)  # Outputs: 15
```
- **Explanation**: For numbers, `+` performs addition, not concatenation.

### Global and Local Variables
Variables created outside functions are **global** and accessible everywhere. Variables inside functions are **local** unless declared with the `global` keyword.

**Example Code (Global Variable)**:
```python
x = "awesome"  # Global variable

def myfunc():
    print("Python is " + x)  # Uses global x

myfunc()  # Outputs: Python is awesome
print("Python is " + x)  # Outputs: Python is awesome
```
- **Explanation**:
  - `x = "awesome"`: Global variable, accessible inside and outside `myfunc`.
  - `print("Python is " + x)`: Uses global `x` in both cases.

**Example Code (Local Variable)**:
```python
x = "awesome"  # Global variable

def myfunc():
    x = "fantastic"  # Local variable
    print("Python is " + x)  # Uses local x

myfunc()  # Outputs: Python is fantastic
print("Python is " + x)  # Outputs: Python is awesome
```
- **Explanation**:
  - Local `x` (`"fantastic"`) inside `myfunc` doesn’t affect global `x` (`"awesome"`).
- **Common Mistake**: Assuming a local variable changes the global one.
  - **Fix**: Local variables are separate unless `global` is used.

**Example Code (Using `global` Keyword)**:
```python
def myfunc():
    global x  # Declares x as global
    x = "fantastic"  # Sets global x

myfunc()
print("Python is " + x)  # Outputs: Python is fantastic
```
- **Explanation**:
  - `global x`: Makes `x` global inside `myfunc`.
  - `x = "fantastic"`: Changes the global `x` value.
- **Common Mistake**: Forgetting `global` when modifying a global variable.
  - **Error Example**:
    ```python
    x = "awesome"
    def myfunc():
        x = "fantastic"  # Creates local x
    myfunc()
    print(x)  # Outputs: awesome (global unchanged)
    ```
  - **Fix**: Use `global x` to modify the global variable.

**One-Line Takeaway**: Python variables are flexible containers for data, with simple assignment, dynamic typing, and specific rules for naming, multiple assignments, output, and scope.

---

## Section 2 — Class Exercise

### Exercise: Create a Profile Printer

**Objective**: Write a Python program that uses variables, type casting, and output methods to print a user profile with multiple data types.

**Step-by-Step Instructions**:
1. Create a file named `profile.py`.
2. Declare variables:
   - `name` (string, e.g., `"Alex"`).
   - `age` (cast a string like `"25"` to an integer).
   - `height` (cast an integer like `175` to a float for height in cm).
3. Use snake_case for variable names.
4. Print a profile summary using commas in `print()`:
   - Format: `Name: [name], Age: [age], Height: [height] cm`.
5. Add a comment explaining each variable’s purpose.
6. Run the program with `python profile.py`.

**Hints**:
- Use `int("25")` to cast a string to an integer.
- Use `float(175)` for a float value.
- Use commas in `print()` to handle different types.

**Checkpoint**:
- Check the output format. Does it include all variables?
- Use `print(type(age))` to verify `age` is an integer.

**Example Output** (for `name = "Alex"`, `age = "25"`, `height = 175`):
```
Name: Alex, Age: 25, Height: 175.0 cm
```

---

## Section 3 — Weekly Project

### Project: Shopping Cart Summary

**Objective**: Create a Python program that uses variables, multiple assignments, and scope to generate a shopping cart summary.

**Milestones**:
1. Create a file named `cart.py`.
2. Declare variables:
   - `item1`, `item2`, `item3` (strings, e.g., `"Apple"`, `"Banana"`, `"Orange"`) using multiple assignment.
   - `price1`, `price2`, `price3` (floats, e.g., `0.5`, `0.3`, `0.6`) using multiple assignment.
   - `total` (sum of prices, calculated globally).
3. Define a function `print_cart()` that:
   - Uses local variables with the same names (`item1`, etc.) for different items.
   - Prints a local summary: `Local Cart: [item1], [item2], [item3]`.
4. Print a global summary outside the function: `Global Cart: [item1], [item2], [item3], Total: [total]`.
5. Add comments to explain each section.

**Deliverables**:
- A working `cart.py` file.
- Output showing both local and global cart summaries.

**Research Prompts**:
- How does the `+` operator behave differently for strings vs. numbers?
- What happens if you try to modify a global variable without the `global` keyword?

**Assessment Criteria**:
- Code runs without errors.
- Variables use snake_case and correct types.
- Function uses local variables without affecting global ones.
- Output includes both summaries with correct values.
- Comments explain key steps.

**Extension Idea**:
- Add a `discount` variable (float, e.g., `0.1` for 10%) and apply it to `total`.
- Use the `global` keyword to modify `total` inside the function.

**Example Output**:
```
Local Cart: Bread, Milk, Eggs
Global Cart: Apple, Banana, Orange, Total: 1.4
```

---

## Completion Checklist
- [ ] Created variables with different types (int, str, float) and printed them.
- [ ] Used casting (`str()`, `int()`, `float()`) and checked types with `type()`.
- [ ] Named variables using snake_case and followed naming rules.
- [ ] Assigned multiple values in one line and unpacked a list.
- [ ] Output variables using `print()` with commas and `+` correctly.
- [ ] Used global and local variables in a function, with and without the `global` keyword.
- [ ] Completed the class exercise and verified the output.
- [ ] Started the weekly project and planned the cart summary.
- [ ] Fixed at least one common mistake (e.g., invalid variable name or type error).