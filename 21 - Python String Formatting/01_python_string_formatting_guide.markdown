# Python String Formatting: Beginner-Friendly Teaching Package

This teaching package transforms the provided lesson note on Python string formatting into a structured, beginner-friendly guide. It covers **f-strings** (introduced in Python 3.6) and the older `format()` method, including placeholders, modifiers, operations, and functions within strings. The goal is to make string formatting accessible while guiding learners toward practical mastery through hands-on exercises and a project.

---

## Section 1 — Topical Explanations

### Learning Goals
By the end of this section, you’ll understand:
- How to use f-strings to format strings dynamically.
- How to use placeholders and modifiers for precise formatting.
- How to perform operations and execute functions within f-strings.
- How to use the older `format()` method with indexed and named placeholders.
- Practical applications of string formatting in real-world scenarios.

### What is String Formatting?
String formatting allows you to insert values (variables, calculations, or function results) into strings dynamically. Think of it like filling in a template with specific data, such as inserting a price into a sentence like “The price is $59.00.” Python offers **f-strings** (preferred since Python 3.6 for their simplicity and speed) and the older `format()` method.

### F-Strings
F-strings are created by prefixing a string with `f` and using curly braces `{}` as placeholders for values.

**Example Code** (basic f-string):
```python
txt = f"The price is 49 dollars"
print(txt)
```

**Line-by-Line Explanation**:
- `txt = f"The price is 49 dollars"`: Defines an f-string with a literal value (no dynamic content yet).
- `print(txt)`: Outputs the string as is.

**Expected Output**:
```
The price is 49 dollars
```

**Visual Description**: The output is a simple string with no dynamic values, showing the basic structure of an f-string.

**Common Mistake**:
- Forgetting the `f` prefix, causing `{}` to be treated as literal braces.
- **Fix**: Always include `f` before the string (e.g., `f"..."`).

**Validation Check**: Change the value to `99` and confirm the output updates to `The price is 99 dollars`.

### Placeholders and Modifiers
Placeholders `{}` in f-strings can contain variables, and modifiers (after a colon `:`) control formatting, like specifying decimal places.

**Example Code** (with variable and modifier):
```python
price = 59
txt = f"The price is {price:.2f} dollars"
print(txt)
```

**Line-by-Line Explanation**:
- `price = 59`: Defines a variable for the price.
- `txt = f"The price is {price:.2f} dollars"`: Uses `{price:.2f}` to insert `price` with 2 decimal places (`.2f` means fixed-point number with 2 decimals).
- `print(txt)`: Outputs the formatted string.

**Expected Output**:
```
The price is 59.00 dollars
```

**Visual Description**: The number `59` is formatted as `59.00`, showing two decimal places, typical for currency.

**Common Mistake**:
- Using incorrect modifiers (e.g., `.2d` instead of `.2f`), causing a `ValueError`.
- **Fix**: Use `.2f` for floating-point numbers, `.2d` for integers.

**Validation Check**: Test with `price = 59.999` and confirm the output is `59.99`.

**Example Code** (direct value with modifier):
```python
txt = f"The price is {95:.2f} dollars"
print(txt)
```

**Explanation**:
- `{95:.2f}`: Formats the literal value `95` directly with 2 decimal places.
- **Output**: `The price is 95.00 dollars`.

**Validation Check**: Change `95` to `123.456` and verify the output is `123.46`.

### Operations in F-Strings
F-strings support Python expressions inside placeholders, such as math operations.

**Example Code** (math operation):
```python
txt = f"The price is {20 * 59} dollars"
print(txt)
```

**Line-by-Line Explanation**:
- `{20 * 59}`: Performs multiplication inside the placeholder.
- `print(txt)`: Outputs the result of the operation.

**Expected Output**:
```
The price is 1180 dollars
```

**Visual Description**: The f-string computes `20 * 59` and inserts `1180` into the string.

**Common Mistake**:
- Writing complex expressions that are hard to read inside `{}`.
- **Fix**: Keep expressions simple or compute them outside the f-string.

**Validation Check**: Change to `{20 * 10}` and confirm the output is `200`.

**Example Code** (operation with variables):
```python
price = 59
tax = 0.25
txt = f"The price is {price + (price * tax)} dollars"
print(txt)
```

**Explanation**:
- `{price + (price * tax)}`: Calculates the total price including tax.
- **Output**: `The price is 73.75 dollars`.

**Validation Check**: Set `tax = 0.1` and verify the output is `64.90`.

### Conditional Statements in F-Strings
F-strings support conditional expressions (e.g., ternary operators).

**Example Code**:
```python
price = 49
txt = f"It is very {'Expensive' if price > 50 else 'Cheap'}"
print(txt)
```

**Line-by-Line Explanation**:
- `{'Expensive' if price > 50 else 'Cheap'}`: Uses a ternary operator to insert `"Expensive"` if `price > 50`, otherwise `"Cheap"`.
- `print(txt)`: Outputs the result.

**Expected Output**:
```
It is very Cheap
```

**Visual Description**: Since `price = 49` is not greater than 50, `"Cheap"` is inserted.

**Common Mistake**:
- Using full `if` statements instead of ternary operators, which aren’t allowed in f-strings.
- **Fix**: Use `value_if_true if condition else value_if_false`.

**Validation Check**: Set `price = 51` and confirm the output is `It is very Expensive`.

### Functions in F-Strings
F-strings can call functions inside placeholders.

**Example Code** (built-in function):
```python
fruit = "apples"
txt = f"I love {fruit.upper()}"
print(txt)
```

**Explanation**:
- `{fruit.upper()}`: Calls the `upper()` method to convert `fruit` to uppercase.
- **Output**: `I love APPLES`.

**Validation Check**: Change `fruit` to `"bananas"` and verify the output is `I love BANANAS`.

**Example Code** (custom function):
```python
def myconverter(x):
    return x * 0.3048
txt = f"The plane is flying at a {myconverter(30000)} meter altitude"
print(txt)
```

**Line-by-Line Explanation**:
- `def myconverter(x): return x * 0.3048`: Defines a function to convert feet to meters.
- `{myconverter(30000)}`: Calls the function with `30000` feet, inserting the result.
- **Output**: `The plane is flying at a 9144.0 meter altitude`.

**Common Mistake**:
- Calling functions that raise errors (e.g., undefined functions) inside f-strings.
- **Fix**: Ensure the function is defined and tested before using it.

**Validation Check**: Change the input to `10000` and confirm the output is `3048.0`.

### More Modifiers
Modifiers format numbers or strings in specific ways, like thousand separators.

**Example Code** (thousand separator):
```python
price = 59000
txt = f"The price is {price:,} dollars"
print(txt)
```

**Explanation**:
- `{price:,}`: Uses `,` as a thousand separator.
- **Output**: `The price is 59,000 dollars`.

**Common Mistake**:
- Using a modifier incompatible with the data type (e.g., `:,` on a string).
- **Fix**: Ensure the modifier matches the value type (e.g., `:,` for numbers).

**Validation Check**: Test with `price = 1234567` and confirm the output is `1,234,567`.

**Other Modifiers** (examples):
- `:<10`: Left-aligns text in a 10-character space.
- `:>10`: Right-aligns text.
- `:.2e`: Scientific notation with 2 decimals.
- `:%`: Formats as a percentage (e.g., `0.75` becomes `75.000000%`).

### The `format()` Method
Before Python 3.6, the `format()` method was used for string formatting.

**Example Code** (basic `format()`):
```python
price = 49
txt = "The price is {} dollars"
print(txt.format(price))
```

**Explanation**:
- `txt = "The price is {} dollars"`: Defines a string with a `{}` placeholder.
- `txt.format(price)`: Inserts `price` into the placeholder.
- **Output**: `The price is 49 dollars`.

**Example Code** (with modifier):
```python
txt = "The price is {:.2f} dollars"
print(txt.format(49))
```

**Explanation**:
- `{:.2f}`: Formats the value as a float with 2 decimals.
- **Output**: `The price is 49.00 dollars`.

### Multiple Values with `format()`
You can insert multiple values using multiple placeholders.

**Example Code**:
```python
quantity = 3
itemno = 567
price = 49
myorder = "I want {} pieces of item number {} for {:.2f} dollars."
print(myorder.format(quantity, itemno, price))
```

**Explanation**:
- `{}`: Placeholders are filled in order by `format()` arguments.
- **Output**: `I want 3 pieces of item number 567 for 49.00 dollars`.

### Indexed Placeholders
You can specify the order of values using indices.

**Example Code**:
```python
quantity = 3
itemno = 567
price = 49
myorder = "I want {0} pieces of item number {1} for {2:.2f} dollars."
print(myorder.format(quantity, itemno, price))
```

**Explanation**:
- `{0}`, `{1}`, `{2}`: Refer to the first, second, and third arguments of `format()`.
- **Output**: Same as above.

**Validation Check**: Swap indices (e.g., `{1} pieces of item number {0}`) and confirm the output changes accordingly.

### Named Indexes
You can use names in placeholders for clarity.

**Example Code**:
```python
myorder = "I have a {carname}, it is a {model}."
print(myorder.format(carname="Ford", model="Mustang"))
```

**Explanation**:
- `{carname}`, `{model}`: Placeholders are filled by named arguments.
- **Output**: `I have a Ford, it is a Mustang`.

**Common Mistake**:
- Mismatching names in `format()` (e.g., `carname` vs. `car`).
- **Fix**: Ensure placeholder names match `format()` arguments.

**Validation Check**: Change to `carname="Toyota", model="Camry"` and verify the output updates.

**One-Line Takeaway**: F-strings and the `format()` method enable dynamic string formatting with placeholders, modifiers, operations, and functions for flexible output.

---

## Section 2 — Class Exercise

### Objectives
- Practice using f-strings with variables, modifiers, and operations.
- Use the `format()` method with indexed and named placeholders.
- Apply string formatting in a real-world scenario.

### Step-by-Step Instructions
1. **Basic F-String**:
   - Write a script that prompts for a product name and price, then uses an f-string to display them with the price formatted to 2 decimals.
2. **Operation in F-String**:
   - Modify the script to include a tax rate (e.g., 10%) and calculate the total price (including tax) in the f-string.
3. **Format() Method**:
   - Rewrite the script using `format()` with named placeholders for the product, price, and total.

### Hints
- Use `input()` for product name and price, and `float()` to convert price.
- Use `{:.2f}` for 2 decimal places in both f-strings and `format()`.
- For tax, multiply price by `(1 + tax_rate)`.

### Checkpoints
- After step 1, test with `Apple` and `2.5` (output: `Apple costs $2.50`).
- After step 2, verify the total includes 10% tax (e.g., `2.75` for `2.5`).
- After step 3, confirm the `format()` output matches the f-string output.

---

## Section 3 — Weekly Project

### Overview
Create a **Receipt Generator Tool** that prompts for multiple items, their quantities, and prices, then generates a formatted receipt with subtotals and a total, using f-strings and `format()`.

### Milestones
1. **Collect Input**:
   - Prompt the user for item names, quantities, and prices in a loop until they type "done".
   - Validate prices are numeric, raising a `ValueError` if not.
2. **Generate Receipt**:
   - Use f-strings to format each item’s line with quantity, name, price, and subtotal (quantity * price).
   - Display the total sum of subtotals with 2 decimals.
3. **Alternative Format**:
   - Provide an option to display the receipt using `format()` with named or indexed placeholders.

### Deliverables
- A Python script that:
  - Collects and validates item details.
  - Prints a formatted receipt using f-strings.
  - Offers a `format()`-based receipt option.
  - Includes comments explaining the code.

### Research Prompts
- How can you align text in f-strings or `format()` for a neat receipt layout?
- What happens if a user enters negative quantities or prices?
- How can you store item details for reuse in both formatting methods?

### Assessment Criteria
- **Correctness**: The script collects inputs, validates prices, and formats the receipt accurately.
- **Clarity**: Code is commented, and the receipt is neatly formatted with aligned text and decimals.
- **Completeness**: Handles errors, supports both f-strings and `format()`, and calculates totals correctly.

### Extension Ideas
- Add a discount feature (e.g., 10% off for totals over $100).
- Save the receipt to a text file.
- Format the receipt as a table with fixed-width columns.

**Sample Approach** (not a full solution):
- Use a list of dictionaries to store items (`{"name": "Apple", "quantity": 2, "price": 1.5}`).
- Use `{:<20}` for left-aligned item names and `{:.2f}` for prices.
- Sum subtotals with `sum(item["quantity"] * item["price"] for item in items)`.

---

## Completion Checklist
- [ ] Understand f-strings and `format()` with placeholders, modifiers, and operations.
- [ ] Run the example codes and verify outputs (e.g., `59.00`, `Expensive`, `9144.0`).
- [ ] Complete the class exercise, confirming correct formatting for product and price.
- [ ] Start the weekly project by writing a script to generate a receipt.
- [ ] Avoid common mistakes like incorrect modifiers or missing `f` in f-strings.

**Common Pitfalls**:
- Forgetting the `f` prefix in f-strings, causing literal `{}` output.
- Using incompatible modifiers (e.g., `:,` on strings).
- Mismatching indices or names in `format()` placeholders.

**One-Line Takeaway**: F-strings and `format()` provide flexible ways to create dynamic, well-formatted strings with variables, operations, and custom formatting.