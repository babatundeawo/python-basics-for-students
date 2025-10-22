# Python Modules, Datetime, Math, and JSON: Beginner-Friendly Teaching Package

This teaching package transforms the lesson note on **Python Modules, Datetime, Math, and JSON** into a beginner-friendly format. It explains key concepts with clear examples, hands-on exercises, and a project to reinforce learning.

---

## Section 1 — Topical Explanations

### 1.1 Python Modules

**What are Modules?**  
A module is a Python file containing functions, variables, or classes that you can reuse in other scripts. Think of it like a toolbox: you create tools (functions or variables) in one file and bring them into your project when needed.

**Example 1: Creating and Using a Module**  
Let’s create a module and use it.

**File: `mymodule.py`**  
```python
# mymodule.py
def greeting(name):
    print("Hello, " + name)

person1 = {
    "name": "John",
    "age": 36,
    "country": "Norway"
}
```

**Main Script:**  
```python
# Import and use the module
import mymodule

mymodule.greeting("Jonathan")  # Call function
print(mymodule.person1["age"])  # Access dictionary
```

**Line-by-Line Explanation (Main Script):**  
- `import mymodule`: Loads `mymodule.py` into the script.  
- `mymodule.greeting("Jonathan")`: Calls the `greeting` function, printing "Hello, Jonathan".  
- `mymodule.person1["age"]`: Accesses the `age` key from the `person1` dictionary.  
- `print(mymodule.person1["age"])`: Outputs `36`.

**Expected Output:**  
```
Hello, Jonathan
36
```

**Visual Description:**  
The console shows a greeting followed by the age `36` on a new line.

**Common Mistakes:**  
- Forgetting the `.py` extension when creating the module file.  
  - **Fix**: Ensure the file is named `mymodule.py`.  
- Using incorrect syntax to access module contents (e.g., `greeting("Jonathan")` without `mymodule.`).  
  - **Fix**: Use `module_name.function_name` or `module_name.variable_name`.  

**Validation Check:**  
What’s the output if you access `mymodule.person1["name"]`? (Answer: `"John"`)

**Example 2: Using an Alias and Built-in Modules**  
You can rename modules with `as` or use built-in modules like `platform`.

```python
# Use alias and platform module
import mymodule as mx
import platform

print(mx.person1["country"])  # Access with alias
print(platform.system())      # Get OS name
```

**Line-by-Line Explanation:**  
- `import mymodule as mx`: Imports `mymodule` with alias `mx`.  
- `mx.person1["country"]`: Accesses the `country` key, outputs `"Norway"`.  
- `import platform`: Imports the built-in `platform` module.  
- `platform.system()`: Returns the operating system (e.g., `"Windows"`, `"Linux"`, or `"Darwin"`).  

**Expected Output (varies by OS):**  
```
Norway
Windows  # Example for Windows OS
```

**Example 3: Using `dir()` and Partial Import**  
List module contents with `dir()` or import specific parts.

```python
# List module contents and import specific part
from mymodule import person1
import platform

print(person1["age"])  # Direct access without module name
print(dir(platform))   # List platform module contents
```

**Line-by-Line Explanation:**  
- `from mymodule import person1`: Imports only the `person1` dictionary.  
- `print(person1["age"])`: Accesses `age` directly, outputs `36`.  
- `dir(platform)`: Lists all attributes and methods of the `platform` module (e.g., `['system', 'platform', ...]`).  
- `print(dir(platform))`: Outputs the list of names.

**Expected Output (partial for `dir`):**  
```
36
['system', 'platform', ...]  # List of platform attributes
```

**Common Mistakes:**  
- Using the module name after `from ... import` (e.g., `mymodule.person1["age"]` → `NameError`).  
  - **Fix**: Use `person1["age"]` directly after importing `person1`.  

**One-Line Takeaway:**  
Modules are reusable Python files containing functions and variables, accessed with `import` and optionally aliased or partially imported.

---

### 1.2 Python Datetime

**What is Datetime?**  
The `datetime` module lets you work with dates and times as objects. Think of it like a calendar and clock combined, allowing you to create, manipulate, and format dates.

**Example 1: Current Date and Time**  
Get the current date and time.

```python
# Get current date and time
import datetime

x = datetime.datetime.now()
print(x)
print(x.year)
print(x.strftime("%A"))
```

**Line-by-Line Explanation:**  
- `import datetime`: Imports the `datetime` module.  
- `x = datetime.datetime.now()`: Creates a `datetime` object for the current date and time (e.g., `2025-10-22 12:14:58.979007`).  
- `print(x)`: Outputs the full datetime.  
- `print(x.year)`: Outputs the year (e.g., `2025`).  
- `print(x.strftime("%A"))`: Formats the date to show the full weekday name (e.g., `"Wednesday"`).

**Expected Output (varies by date):**  
```
2025-10-22 12:14:58.979007
2025
Wednesday
```

**Visual Description:**  
The console shows the full datetime, followed by the year and weekday on new lines.

**Common Mistakes:**  
- Forgetting to use `datetime.datetime` (e.g., `datetime.now()` → `AttributeError`).  
  - **Fix**: Use the full path `datetime.datetime.now()`.  
- Using incorrect format codes (e.g., `%a` for full weekday instead of `%A`).  
  - **Fix**: Check the format code reference (e.g., `%A` for "Wednesday", `%a` for "Wed").

**Validation Check:**  
What does `x.strftime("%B")` output? (Answer: `"October"` for October 2025)

**Example 2: Creating and Formatting Dates**  
Create a specific date and format it.

```python
# Create and format a date
import datetime

x = datetime.datetime(2020, 5, 17)
print(x)
print(x.strftime("%B"))
```

**Line-by-Line Explanation:**  
- `x = datetime.datetime(2020, 5, 17)`: Creates a `datetime` object for May 17, 2020.  
- `print(x)`: Outputs `2020-05-17 00:00:00` (time defaults to 00:00:00).  
- `x.strftime("%B")`: Formats the date to show the full month name (`"May"`).  

**Expected Output:**  
```
2020-05-17 00:00:00
May
```

**One-Line Takeaway:**  
The `datetime` module enables working with dates and times, with `strftime()` for formatting into readable strings.

---

### 1.3 Python Math

**What is the Math Module?**  
The `math` module provides functions and constants for mathematical operations, like a calculator with advanced features. Built-in functions like `min()`, `max()`, `abs()`, and `pow()` are also available without importing.

**Example 1: Built-in Math Functions**  
Use built-in math functions without importing.

```python
# Built-in math functions
x = min(5, 10, 25)
y = max(5, 10, 25)
z = abs(-7.25)
w = pow(4, 3)
print(x, y, z, w)
```

**Line-by-Line Explanation:**  
- `min(5, 10, 25)`: Returns the smallest value (`5`).  
- `max(5, 10, 25)`: Returns the largest value (`25`).  
- `abs(-7.25)`: Returns the absolute value (`7.25`).  
- `pow(4, 3)`: Computes 4^3 (`4 * 4 * 4 = 64`).  
- `print(x, y, z, w)`: Outputs all results.

**Expected Output:**  
```
5 25 7.25 64
```

**Visual Description:**  
The console shows four numbers separated by spaces.

**Common Mistakes:**  
- Passing non-numeric values to `min()` or `max()` (e.g., `min("a", "b")` → depends on string comparison).  
  - **Fix**: Ensure inputs are comparable (e.g., numbers).  

**Validation Check:**  
What’s `pow(2, 3)`? (Answer: `8`)

**Example 2: Math Module Functions**  
Use the `math` module for advanced calculations.

```python
# Math module functions
import math

x = math.sqrt(64)
y = math.ceil(1.4)
z = math.floor(1.4)
w = math.pi
print(x, y, z, w)
```

**Line-by-Line Explanation:**  
- `import math`: Imports the `math` module.  
- `math.sqrt(64)`: Returns the square root (`8.0`).  
- `math.ceil(1.4)`: Rounds up to the nearest integer (`2`).  
- `math.floor(1.4)`: Rounds down to the nearest integer (`1`).  
- `math.pi`: Returns the constant π (`3.141592653589793`).  
- `print(x, y, z, w)`: Outputs all results.

**Expected Output:**  
```
8.0 2 1 3.141592653589793
```

**Common Mistakes:**  
- Forgetting to import `math` (e.g., `sqrt(64)` → `NameError`).  
  - **Fix**: Import `math` first.  
- Using `math.sqrt()` with negative numbers (e.g., `math.sqrt(-1)` → `ValueError`).  
  - **Fix**: Ensure non-negative inputs.

**One-Line Takeaway:**  
The `math` module and built-in functions like `min()`, `max()`, and `pow()` provide tools for mathematical operations.

---

### 1.4 Python JSON

**What is JSON?**  
JSON (JavaScript Object Notation) is a lightweight format for storing and exchanging data. Python’s `json` module converts between JSON strings and Python objects, like a translator between two languages.

**Example 1: Parsing JSON to Python**  
Convert a JSON string to a Python dictionary.

```python
# Parse JSON to Python
import json

x = '{"name": "John", "age": 30, "city": "New York"}'
y = json.loads(x)
print(y["age"])
```

**Line-by-Line Explanation:**  
- `import json`: Imports the `json` module.  
- `x = '{"name": ...}'`: Defines a JSON string.  
- `json.loads(x)`: Converts the JSON string to a Python dictionary.  
- `y["age"]`: Accesses the `age` key, outputs `30`.  
- `print(y["age"])`: Outputs the value.

**Expected Output:**  
```
30
```

**Visual Description:**  
The console shows the number `30`.

**Common Mistakes:**  
- Invalid JSON syntax (e.g., single quotes in JSON).  
  - **Fix**: Use double quotes in JSON strings (e.g., `"name"`, not `'name'`).  
- Accessing non-existent keys (e.g., `y["country"]` → `KeyError`).  
  - **Fix**: Check dictionary keys with `in`.

**Validation Check:**  
What’s `y["name"]`? (Answer: `"John"`)

**Example 2: Converting Python to JSON**  
Convert a Python dictionary to a JSON string.

```python
# Convert Python to JSON
import json

x = {
    "name": "John",
    "age": 30,
    "married": True,
    "children": ("Ann", "Billy"),
    "pets": None,
    "cars": [
        {"model": "BMW 230", "mpg": 27.5},
        {"model": "Ford Edge", "mpg": 24.1}
    ]
}
y = json.dumps(x, indent=4)
print(y)
```

**Line-by-Line Explanation:**  
- `x = {...}`: Defines a complex Python dictionary with various data types.  
- `json.dumps(x, indent=4)`: Converts to a formatted JSON string with 4-space indentation.  
- `print(y)`: Outputs the JSON string.

**Expected Output:**  
```json
{
    "name": "John",
    "age": 30,
    "married": true,
    "children": [
        "Ann",
        "Billy"
    ],
    "pets": null,
    "cars": [
        {
            "model": "BMW 230",
            "mpg": 27.5
        },
        {
            "model": "Ford Edge",
            "mpg": 24.1
        }
    ]
}
```

**Common Mistakes:**  
- Using unsupported Python types (e.g., complex objects) in `json.dumps()`.  
  - **Fix**: Use JSON-compatible types (dict, list, str, int, float, bool, None).  

**One-Line Takeaway:**  
The `json` module converts between Python objects and JSON strings for data storage and exchange.

---

## Section 2 — Class Exercise

**Exercise: Module and JSON Practice**

**Objectives:**  
- Create and use a custom module with a function and variable.  
- Work with JSON to parse and create data.  

**Step-by-Step Instructions:**  
1. Create a module `utils.py` with a function `square(num)` that returns the square of a number and a variable `settings = {"theme": "dark", "font_size": 12}`.  
2. In a main script, import `utils`, call `square(5)`, and print `settings["theme"]`.  
3. Parse a JSON string `{"title": "Book", "price": 29.99}` and print the price.  
4. Create a Python dictionary `{"item": "Laptop", "in_stock": True}` and convert it to a JSON string with indentation.  

**Hints:**  
- Save `utils.py` in the same directory as your main script.  
- Use `json.loads()` for parsing and `json.dumps()` with `indent=4` for formatting.  
- Check JSON syntax (double quotes, valid types).  

**Checkpoints:**  
- Does `square(5)` return `25`?  
- Does `settings["theme"]` return `"dark"`?  
- Does the JSON parse return `29.99` for price?  
- Is the JSON output formatted with indentation?  

---

## Section 3 — Weekly Project

**Project: Task Tracker**

**Overview:**  
Create a program that uses modules, `datetime`, `math`, and `json` to manage a task list. Users can add tasks, view tasks with due dates, and calculate task priorities.

**Milestones:**  
1. **Create a Module:** Create a module `task_utils.py` with a function to calculate priority (based on a formula) and a default task template dictionary.  
2. **Add Tasks:** Prompt the user to input tasks (name and due date) and store them in a list as JSON-compatible dictionaries.  
3. **Display Tasks:** Show tasks with their due dates formatted using `datetime`.  
4. **Calculate Priorities:** Use the module’s priority function to compute and display a priority score for each task using `math`.  

**Deliverables:**  
- A module `task_utils.py` with a priority function and task template.  
- A main script that:  
  - Collects tasks with names and due dates.  
  - Stores tasks as dictionaries in a list.  
  - Displays tasks with formatted dates.  
  - Calculates and shows priority scores.  
- Comments explaining each part.  

**Research Prompts:**  
- How do modules improve code organization?  
- Why use `datetime` for date handling instead of strings?  
- How does JSON help with data storage across programs?  

**Assessment Criteria:**  
- Module correctly defines the priority function and template.  
- Tasks are collected and stored correctly.  
- Due dates are formatted using `datetime`.  
- Priority scores are calculated using `math`.  
- Code is well-commented and error-free.  

**Extension Ideas:**  
- Save tasks to a JSON file using `json.dump()`.  
- Sort tasks by priority using `sort()`.  
- Add a feature to filter tasks due this week using `datetime`.  

---

## Completion Checklist

- [ ] Created and used a custom module with functions and variables.  
- [ ] Worked with `datetime` to create and format dates.  
- [ ] Used `math` module for calculations like `sqrt` or `ceil`.  
- [ ] Parsed and created JSON data with `json.loads()` and `json.dumps()`.  
- [ ] Completed the class exercise and verified outputs.  
- [ ] Started the weekly project with at least one milestone completed.  
- [ ] Avoided pitfalls like incorrect module imports or invalid JSON syntax.  

**One-Line Takeaway Summary:**  
Python’s modules, `datetime`, `math`, and `json` enable modular code, date handling, mathematical operations, and data exchange for robust applications.