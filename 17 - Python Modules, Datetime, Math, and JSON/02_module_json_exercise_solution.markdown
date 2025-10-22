# Solution to Module and JSON Practice Exercise

This document provides a solution to the **Module and JSON Practice** exercise from the Python Modules, Datetime, Math, and JSON teaching package. It includes the code, a detailed explanation, and verification of the expected outputs.

---

## Exercise Overview

**Objectives:**

- Create and use a custom module with a function and variable.
- Work with JSON to parse and create data.

**Tasks:**

1. Create a module `utils.py` with a function `square(num)` that returns the square of a number and a variable `settings = {"theme": "dark", "font_size": 12}`.
2. In a main script, import `utils`, call `square(5)`, and print `settings["theme"]`.
3. Parse a JSON string `{"title": "Book", "price": 29.99}` and print the price.
4. Create a Python dictionary `{"item": "Laptop", "in_stock": True}` and convert it to a JSON string with indentation.

**Expected Outputs:**

- Task 2: `25` (from `square(5)`) and `"dark"` (from `settings["theme"]`).

- Task 3: `29.99` (from parsed JSON).

- Task 4: A formatted JSON string:

  ```json
  {
      "item": "Laptop",
      "in_stock": true
  }
  ```

---

## Solution Code

**File:** `utils.py`

```python
# utils.py
def square(num):
    return num * num

settings = {
    "theme": "dark",
    "font_size": 12
}
```

**File:** `main.py`

```python
# Main script for Module and JSON Practice Exercise
import utils
import json

# Task 2: Use the utils module
print("Square of 5:", utils.square(5))
print("Theme setting:", utils.settings["theme"])

# Task 3: Parse JSON string
json_string = '{"title": "Book", "price": 29.99}'
parsed_data = json.loads(json_string)
print("Book price:", parsed_data["price"])

# Task 4: Convert Python dictionary to JSON
data = {
    "item": "Laptop",
    "in_stock": True
}
json_output = json.dumps(data, indent=4)
print("JSON output:\n", json_output)
```

---

## Explanation

### Task 1: Create the Module (`utils.py`)

**Code Breakdown:**

- **Function**: `square(num)`
  - Takes a number `num` and returns its square (`num * num`).
- **Variable**: `settings`
  - A dictionary with keys `"theme"` and `"font_size"`, set to `"dark"` and `12`, respectively.
- **File**: Saved as `utils.py` in the same directory as the main script.

**Why It Works:**

- The module defines reusable components: a function (`square`) and a variable (`settings`).
- Saving as `utils.py` ensures it can be imported by the main script.

**Common Pitfalls and Fixes:**

- **Pitfall**: Saving the file with a different name or extension (e.g., `utils.txt`).
  - **Fix**: Ensure the file is named `utils.py`.
- **Pitfall**: Incorrect module structure (e.g., syntax errors in `utils.py`).
  - **Fix**: Verify the module code is valid Python.

**Validation Check:**

- The module is correctly set up if it can be imported without errors.

### Task 2: Use the Module in the Main Script

**Code Breakdown:**

- `import utils`: Imports the `utils` module.
- `utils.square(5)`: Calls the `square` function with `5`, returning `25`.
- `utils.settings["theme"]`: Accesses the `"theme"` key from the `settings` dictionary, returning `"dark"`.
- `print("Square of 5:", utils.square(5))`: Outputs the square with a label.
- `print("Theme setting:", utils.settings["theme"])`: Outputs the theme with a label.

**Expected Output:**

```
Square of 5: 25
Theme setting: dark
```

**Why It Works:**

- The `import utils` statement loads `utils.py`, making its contents accessible.
- The dot notation (`utils.square` and `utils.settings`) correctly references the module’s function and variable.
- The outputs match the expected values (`25` and `"dark"`).

**Common Pitfalls and Fixes:**

- **Pitfall**: Forgetting the module name (e.g., `square(5)` → `NameError`).
  - **Fix**: Use `utils.square(5)`.
- **Pitfall**: Accessing a non-existent key (e.g., `utils.settings["color"]` → `KeyError`).
  - **Fix**: Verify dictionary keys with `in` or check `utils.py`.

**Validation Check:**

- The outputs `25` and `"dark"` match the checkpoints.

### Task 3: Parse JSON String

**Code Breakdown:**

- `json_string = '{"title": "Book", "price": 29.99}'`: Defines a JSON string.
- `parsed_data = json.loads(json_string)`: Converts the JSON string to a Python dictionary.
- `parsed_data["price"]`: Accesses the `"price"` key, returning `29.99`.
- `print("Book price:", parsed_data["price"])`: Outputs the price with a label.

**Expected Output:**

```
Book price: 29.99
```

**Why It Works:**

- `json.loads()` correctly parses the JSON string into a dictionary.
- The `"price"` key is accessed to retrieve the value `29.99`.
- The print statement formats the output clearly.

**Common Pitfalls and Fixes:**

- **Pitfall**: Invalid JSON syntax (e.g., using single quotes: `'title'`).
  - **Fix**: Use double quotes in JSON strings (e.g., `"title"`).
- **Pitfall**: Accessing a non-existent key (e.g., `parsed_data["cost"]` → `KeyError`).
  - **Fix**: Check keys with `in` (e.g., `"price" in parsed_data`).

**Validation Check:**

- The output `29.99` matches the checkpoint.

### Task 4: Convert Python Dictionary to JSON

**Code Breakdown:**

- `data = {"item": "Laptop", "in_stock": True}`: Defines a Python dictionary.
- `json.dumps(data, indent=4)`: Converts the dictionary to a JSON string with 4-space indentation.
- `print("JSON output:\n", json_output)`: Outputs the formatted JSON string.

**Expected Output:**

```
JSON output:
 {
    "item": "Laptop",
    "in_stock": true
}
```

**Why It Works:**

- `json.dumps()` converts the dictionary to a JSON string, mapping Python `True` to JSON `true`.
- The `indent=4` parameter formats the output for readability with proper indentation.
- The print statement includes a newline (`\n`) for clarity.

**Common Pitfalls and Fixes:**

- **Pitfall**: Using non-JSON-serializable types (e.g., custom objects).
  - **Fix**: Use JSON-compatible types (dict, list, str, int, float, bool, None).
- **Pitfall**: Forgetting indentation, making the output hard to read.
  - **Fix**: Use `indent=4` for formatted output.

**Validation Check:**

- The output is a properly formatted JSON string with `"item": "Laptop"` and `"in_stock": true`.

---

## Running the Code

1. Save the module code as `utils.py`.
2. Save the main script as `main.py` in the same directory.
3. Run `main.py` in a Python environment.

The output will show:

- The square of 5: `25`.
- The theme setting: `"dark"`.
- The book price: `29.99`.
- A formatted JSON string for the dictionary `{"item": "Laptop", "in_stock": True}`.

---

## Completion Checklist

- [ ] Created `utils.py` with `square()` function and `settings` dictionary.

- [ ] Imported `utils` and printed `square(5)` (`25`) and `settings["theme"]` (`"dark"`).

- [ ] Parsed JSON string and printed `"price"` (`29.99`).

- [ ] Converted a dictionary to a formatted JSON string.

- [ ] Verified outputs match the expected results.

- [ ] Avoided pitfalls like incorrect module imports or invalid JSON syntax.

**One-Line Takeaway:**\
The exercise demonstrates how to create and use a module for reusable code and handle JSON data with `json.loads()` and `json.dumps()`.