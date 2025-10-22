# Python String Formatting Class Exercise: Solutions and Explanations

This Markdown file provides the solutions to the class exercise from the Python String Formatting teaching package, along with detailed explanations. The exercise focuses on using **f-strings** and the `format()` method to format product details, including prices with tax, in a real-world scenario. Each solution includes step-by-step instructions, expected outputs, visual descriptions, common mistakes, and validation checks, adhering to the beginner-friendly instructional framework.

---

## Exercise Objectives
- Practice using f-strings with variables, modifiers, and operations.
- Use the `format()` method with indexed and named placeholders.
- Apply string formatting in a real-world scenario (displaying product details with tax).

## Exercise Tasks
1. **Basic F-String**:
   - Write a script that prompts for a product name and price, then uses an f-string to display them with the price formatted to 2 decimal places.
2. **Operation in F-String**:
   - Modify the script to include a tax rate (e.g., 10%) and calculate the total price (including tax) in the f-string.
3. **Format() Method**:
   - Rewrite the script using `format()` with named placeholders for the product, price, and total.

---

## Solution

Below is the complete Python script that addresses all tasks.

```python
# Step 1 & 2: F-String with tax calculation
product = input("Enter the product name: ")
price_input = input("Enter the price: ")

try:
    price = float(price_input)
    tax_rate = 0.10  # 10% tax
    total_price = price * (1 + tax_rate)
    f_string_output = f"{product} costs ${price:.2f}, with 10% tax: ${total_price:.2f}"
    print(f_string_output)
except ValueError:
    print("Error: Price must be a numeric value")

# Step 3: Format() method with named placeholders
try:
    format_string = "{product} costs ${price:.2f}, with 10% tax: ${total:.2f}"
    format_output = format_string.format(
        product=product,
        price=price,
        total=total_price
    )
    print("Using format():", format_output)
except NameError:
    print("Error: Price was not valid, cannot use format()")
```

---

## Explanations

### Task 1: Basic F-String
**Objective**: Prompt for a product name and price, then use an f-string to display them with the price formatted to 2 decimal places.

**Relevant Code**:
```python
product = input("Enter the product name: ")
price_input = input("Enter the price: ")
try:
    price = float(price_input)
    f_string_output = f"{product} costs ${price:.2f}"
    print(f_string_output)
except ValueError:
    print("Error: Price must be a numeric value")
```

**Line-by-Line Explanation**:
- `product = input("Enter the product name: ")`: Prompts for the product name (e.g., `Apple`).
- `price_input = input("Enter the price: ")`: Gets the price as a string.
- `try:`: Starts error handling for numeric conversion.
- `price = float(price_input)`: Converts the price to a float, raising `ValueError` if non-numeric.
- `f"{product} costs ${price:.2f}"`: Uses an f-string with `{product}` for the name and `{price:.2f}` to format the price with 2 decimal places.
- `print(f_string_output)`: Outputs the formatted string.
- `except ValueError:`: Catches invalid numeric inputs and prints an error.

**Expected Output** (for inputs `Apple` and `2.5`):
```
Enter the product name: Apple
Enter the price: 2.5
Apple costs $2.50
```

**Visual Description**: The script prompts for a product and price, then displays the product name and price formatted as currency (e.g., `$2.50` with 2 decimals).

**Common Mistake**:
- Forgetting the `f` prefix, causing `{}` to appear literally in the output.
- **Fix**: Ensure the string starts with `f` (e.g., `f"{product}..."`).

**Validation Check**: Test with `Apple` and `2.5` (output: `Apple costs $2.50`) and with `Banana` and `10` (output: `Banana costs $10.00`).

### Task 2: Operation in F-String
**Objective**: Include a 10% tax rate and calculate the total price (including tax) in the f-string.

**Relevant Code** (integrated in the full script):
```python
try:
    price = float(price_input)
    tax_rate = 0.10
    total_price = price * (1 + tax_rate)
    f_string_output = f"{product} costs ${price:.2f}, with 10% tax: ${total_price:.2f}"
    print(f_string_output)
except ValueError:
    print("Error: Price must be a numeric value")
```

**Line-by-Line Explanation**:
- `tax_rate = 0.10`: Defines a 10% tax rate.
- `total_price = price * (1 + tax_rate)`: Calculates the total price (e.g., for `price = 2.5`, computes `2.5 * 1.1 = 2.75`).
- `f"{product} costs ${price:.2f}, with 10% tax: ${total_price:.2f}"`: Uses an f-string to format both the original price and total price with 2 decimals.
- `except ValueError:`: Ensures non-numeric inputs are caught.

**Expected Output** (for inputs `Apple` and `2.5`):
```
Enter the product name: Apple
Enter the price: 2.5
Apple costs $2.50, with 10% tax: $2.75
```

**Visual Description**: The output shows the product name, original price (e.g., `$2.50`), and total price with tax (e.g., `$2.75`), both formatted to 2 decimal places.

**Common Mistake**:
- Incorrect tax calculation (e.g., adding `price + tax_rate` instead of multiplying).
- **Fix**: Use `price * (1 + tax_rate)` to include the original price plus tax.

**Validation Check**: Test with `Apple` and `10` (output: `Apple costs $10.00, with 10% tax: $11.00`) and with `Banana` and `5.99` (output: `$5.99` and `$6.59`).

### Task 3: Format() Method
**Objective**: Rewrite the script using `format()` with named placeholders for the product, price, and total.

**Relevant Code**:
```python
try:
    format_string = "{product} costs ${price:.2f}, with 10% tax: ${total:.2f}"
    format_output = format_string.format(
        product=product,
        price=price,
        total=total_price
    )
    print("Using format():", format_output)
except NameError:
    print("Error: Price was not valid, cannot use format()")
```

**Line-by-Line Explanation**:
- `format_string = "{product} costs ${price:.2f}, with 10% tax: ${total:.2f}"`: Defines a string with named placeholders `{product}`, `{price:.2f}`, and `{total:.2f}`.
- `format_string.format(product=product, price=price, total=total_price)`: Fills placeholders with named arguments.
- `print("Using format():", format_output)`: Outputs the formatted string, prefixed to distinguish it from the f-string output.
- `except NameError:`: Catches cases where `price` or `total_price` are undefined due to a prior `ValueError`.

**Expected Output** (for inputs `Apple` and `2.5`):
```
Enter the product name: Apple
Enter the price: 2.5
Apple costs $2.50, with 10% tax: $2.75
Using format(): Apple costs $2.50, with 10% tax: $2.75
```

**Expected Output** (for inputs `Apple` and `abc`):
```
Enter the product name: Apple
Enter the price: abc
Error: Price must be a numeric value
Error: Price was not valid, cannot use format()
```

**Visual Description**: The `format()` output matches the f-string output when inputs are valid, showing the product, price, and total with tax. For invalid inputs, both sections display appropriate error messages.

**Common Mistake**:
- Mismatching placeholder names in `format()` (e.g., `{product}` but `format(prod=...)`).
- **Fix**: Ensure names in the string match the `format()` arguments.

**Validation Check**: Confirm the `format()` output matches the f-string output for valid inputs (e.g., `Apple`, `2.5`) and that errors are caught for invalid inputs (e.g., `abc`).

---

## Completion Checklist
- [ ] Ran the script with `Apple` and `2.5`, verifying f-string output (`$2.50`, `$2.75`).
- [ ] Confirmed the `format()` output matches the f-string output.
- [ ] Tested with `Banana` and `5.99`, verifying outputs `$5.99` and `$6.59`.
- [ ] Tested with invalid input (`abc`) and confirmed error messages for both f-string and `format()`.
- [ ] Used `{:.2f}` for consistent 2-decimal formatting.

**Common Pitfalls**:
- Forgetting the `f` prefix in f-strings, causing literal `{}` output.
- Incorrect tax calculation (e.g., adding tax instead of multiplying).
- Not handling `ValueError` for non-numeric inputs, causing crashes.

**One-Line Takeaway**: The script uses f-strings and `format()` to format product details with prices and tax, handling errors to ensure robust user input processing.