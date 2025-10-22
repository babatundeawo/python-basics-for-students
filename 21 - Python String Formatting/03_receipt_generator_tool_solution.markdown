# Python String Formatting Weekly Project: Receipt Generator Tool Solution and Explanation

This Markdown file provides the solution to the weekly project from the Python String Formatting teaching package, which involves creating a **Receipt Generator Tool** that collects item details, validates inputs, and generates a formatted receipt using both f-strings and the `format()` method. The solution includes a complete, beginner-friendly Python script with detailed explanations, adhering to the instructional framework for clarity and hands-on learning.

---

## Project Overview
The goal is to create a Python script that:
- Prompts the user for item names, quantities, and prices in a loop until they type "done".
- Validates prices as numeric, raising a `ValueError` if invalid.
- Generates a receipt with each item’s quantity, name, price, and subtotal (quantity * price), plus a total sum.
- Uses f-strings for the primary receipt and offers an option to display it using `format()` with named or indexed placeholders.
- Includes comments for clarity and handles errors gracefully.

---

## Solution

Below is the complete Python script for the Receipt Generator Tool.

```python
def validate_price(price_input):
    """
    Validates that the price input is a non-negative number.
    Args:
        price_input (str): User input for price.
    Returns:
        float: Validated price.
    Raises:
        ValueError: If input is not a valid non-negative number.
    """
    try:
        price = float(price_input)
        if price < 0:
            raise ValueError("Price cannot be negative")
        return price
    except ValueError:
        raise ValueError("Price must be a numeric value")

def validate_quantity(quantity_input):
    """
    Validates that the quantity input is a positive integer.
    Args:
        quantity_input (str): User input for quantity.
    Returns:
        int: Validated quantity.
    Raises:
        ValueError: If input is not a valid positive integer.
    """
    try:
        quantity = int(quantity_input)
        if quantity <= 0:
            raise ValueError("Quantity must be a positive integer")
        return quantity
    except ValueError:
        raise ValueError("Quantity must be a positive integer")

def format_receipt_fstring(items):
    """
    Formats the receipt using f-strings.
    Args:
        items (list): List of dictionaries with item details.
    Returns:
        str: Formatted receipt string.
    """
    receipt = "Receipt\n" + "-" * 40 + "\n"
    total = 0
    for item in items:
        subtotal = item["quantity"] * item["price"]
        total += subtotal
        receipt += f"{item['quantity']} x {item['name']:<20} @ ${item['price']:.2f} = ${subtotal:.2f}\n"
    receipt += "-" * 40 + f"\nTotal: ${total:.2f}"
    return receipt

def format_receipt_format_method(items):
    """
    Formats the receipt using the format() method with named placeholders.
    Args:
        items (list): List of dictionaries with item details.
    Returns:
        str: Formatted receipt string.
    """
    receipt = "Receipt (using format())\n" + "-" * 40 + "\n"
    total = 0
    for item in items:
        subtotal = item["quantity"] * item["price"]
        total += subtotal
        receipt += "{quantity} x {name:<20} @ ${price:.2f} = ${subtotal:.2f}\n".format(
            quantity=item["quantity"],
            name=item["name"],
            price=item["price"],
            subtotal=subtotal
        )
    receipt += "-" * 40 + "\nTotal: ${total:.2f}".format(total=total)
    return receipt

def main():
    """Main function to run the Receipt Generator Tool."""
    print("Welcome to the Receipt Generator Tool!")
    print("Enter item details (name, quantity, price) or 'done' to finish.")
    
    items = []
    while True:
        name = input("\nEnter item name (or 'done'): ").strip()
        if name.lower() == "done":
            break
        
        try:
            quantity_input = input("Enter quantity: ").strip()
            quantity = validate_quantity(quantity_input)
            price_input = input("Enter price per item: ").strip()
            price = validate_price(price_input)
            items.append({"name": name, "quantity": quantity, "price": price})
        except ValueError as e:
            print(f"Error: {e}")
            continue
    
    if not items:
        print("No items entered. Exiting.")
        return
    
    # Generate and print receipts
    print("\nUsing f-strings:")
    print(format_receipt_fstring(items))
    
    choice = input("\nShow receipt using format() method? (y/n): ").strip().lower()
    if choice == "y":
        print("\n" + format_receipt_format_method(items))

if __name__ == "__main__":
    main()
```

---

## Explanation

### Learning Goals
- Use f-strings and `format()` to format structured output (receipts).
- Validate user inputs with `try-except` and `raise` for error handling.
- Organize data in a list of dictionaries for flexible formatting.
- Apply modifiers (e.g., `{:<20}`, `{:.2f}`) for aligned, formatted output.

### Code Breakdown
Here’s a detailed explanation of the script, designed for beginners.

#### Function: `validate_price`
```python
def validate_price(price_input):
    try:
        price = float(price_input)
        if price < 0:
            raise ValueError("Price cannot be negative")
        return price
    except ValueError:
        raise ValueError("Price must be a numeric value")
```
- **Purpose**: Ensures the price input is a non-negative number.
- **Key Code**:
  - `float(price_input)`: Converts input to a float, raising `ValueError` if non-numeric.
  - `if price < 0`: Checks for negative prices, raising a `ValueError`.
  - `except ValueError`: Catches conversion errors and re-raises with a clear message.
- **Returns**: A valid float price.

**Common Mistake**: Not validating for negative prices, allowing unrealistic inputs.
- **Fix**: Include the `price < 0` check.

#### Function: `validate_quantity`
```python
def validate_quantity(quantity_input):
    try:
        quantity = int(quantity_input)
        if quantity <= 0:
            raise ValueError("Quantity must be a positive integer")
        return quantity
    except ValueError:
        raise ValueError("Quantity must be a positive integer")
```
- **Purpose**: Ensures the quantity is a positive integer.
- **Key Code**:
  - `int(quantity_input)`: Converts input to an integer, raising `ValueError` if invalid.
  - `if quantity <= 0`: Rejects non-positive quantities.
- **Returns**: A valid integer quantity.

**Common Mistake**: Allowing non-integer quantities (e.g., `2.5` items).
- **Fix**: Use `int()` instead of `float()`.

#### Function: `format_receipt_fstring`
```python
def format_receipt_fstring(items):
    receipt = "Receipt\n" + "-" * 40 + "\n"
    total = 0
    for item in items:
        subtotal = item["quantity"] * item["price"]
        total += subtotal
        receipt += f"{item['quantity']} x {item['name']:<20} @ ${item['price']:.2f} = ${subtotal:.2f}\n"
    receipt += "-" * 40 + f"\nTotal: ${total:.2f}"
    return receipt
```
- **Purpose**: Formats the receipt using f-strings.
- **Key Code**:
  - `receipt = "Receipt\n" + "-" * 40`: Starts with a header and separator.
  - `subtotal = item["quantity"] * item["price"]`: Calculates the subtotal.
  - `{item['name']:<20}`: Left-aligns the item name in a 20-character space.
  - `{item['price']:.2f}`: Formats price and subtotal with 2 decimals.
  - `total += subtotal`: Accumulates the total.
  - `f"\nTotal: ${total:.2f}"`: Adds the formatted total.
- **Returns**: A string representing the receipt.

**Common Mistake**: Misaligning text or forgetting decimal formatting.
- **Fix**: Use `{:<20}` for alignment and `{:.2f}` for prices.

#### Function: `format_receipt_format_method`
```python
def format_receipt_format_method(items):
    receipt = "Receipt (using format())\n" + "-" * 40 + "\n"
    total = 0
    for item in items:
        subtotal = item["quantity"] * item["price"]
        total += subtotal
        receipt += "{quantity} x {name:<20} @ ${price:.2f} = ${subtotal:.2f}\n".format(
            quantity=item["quantity"],
            name=item["name"],
            price=item["price"],
            subtotal=subtotal
        )
    receipt += "-" * 40 + "\nTotal: ${total:.2f}".format(total=total)
    return receipt
```
- **Purpose**: Formats the receipt using `format()` with named placeholders.
- **Key Code**:
  - Similar structure to `format_receipt_fstring` but uses `format()` with named placeholders.
  - `{name:<20}`: Aligns the item name.
  - `{price:.2f}`: Formats prices.
- **Returns**: A string matching the f-string receipt format.

**Common Mistake**: Mismatching placeholder names in `format()`.
- **Fix**: Ensure names like `quantity`, `name` match `format()` arguments.

#### Main Function
```python
def main():
    print("Welcome to the Receipt Generator Tool!")
    print("Enter item details (name, quantity, price) or 'done' to finish.")
    items = []
    while True:
        name = input("\nEnter item name (or 'done'): ").strip()
        if name.lower() == "done":
            break
        try:
            quantity_input = input("Enter quantity: ").strip()
            quantity = validate_quantity(quantity_input)
            price_input = input("Enter price per item: ").strip()
            price = validate_price(price_input)
            items.append({"name": name, "quantity": quantity, "price": price})
        except ValueError as e:
            print(f"Error: {e}")
            continue
    if not items:
        print("No items entered. Exiting.")
        return
    print("\nUsing f-strings:")
    print(format_receipt_fstring(items))
    choice = input("\nShow receipt using format() method? (y/n): ").strip().lower()
    if choice == "y":
        print("\n" + format_receipt_format_method(items))
```
- **Purpose**: Manages user input and receipt generation.
- **Key Code**:
  - `items = []`: Stores item details as dictionaries.
  - `while True`: Loops until "done".
  - `try-except`: Catches `ValueError` from validation functions.
  - `items.append({"name": name, "quantity": quantity, "price": price})`: Stores valid item data.
  - `format_receipt_fstring(items)`: Generates f-string receipt.
  - `format_receipt_format_method(items)`: Optionally generates `format()` receipt.

**Expected Output** (example interaction):
```
Welcome to the Receipt Generator Tool!
Enter item details (name, quantity, price) or 'done' to finish.

Enter item name (or 'done'): Apple
Enter quantity: 2
Enter price per item: 1.50
Enter item name (or 'done'): Banana
Enter quantity: 3
Enter price per item: 0.75
Enter item name (or 'done'): done

Using f-strings:
Receipt
----------------------------------------
2 x Apple                 @ $1.50 = $3.00
3 x Banana                @ $0.75 = $2.25
----------------------------------------
Total: $5.25

Show receipt using format() method? (y/n): y

Receipt (using format())
----------------------------------------
2 x Apple                 @ $1.50 = $3.00
3 x Banana                @ $0.75 = $2.25
----------------------------------------
Total: $5.25
```

**Expected Output** (with invalid input):
```
Enter item name (or 'done'): Apple
Enter quantity: 2
Enter price per item: abc
Error: Price must be a numeric value
Enter item name (or 'done'): done
No items entered. Exiting.
```

**Visual Description**: The script prompts for item details, validates inputs, and displays a neatly formatted receipt with aligned item names, prices, and subtotals. The `format()` version matches the f-string output if requested. Errors (e.g., non-numeric prices) are caught and reported.

**Common Mistake**: Not validating inputs, allowing invalid data to crash the script.
- **Fix**: Use `validate_price` and `validate_quantity` with `try-except`.

**Validation Checks**:
- Test with valid inputs (e.g., `Apple`, `2`, `1.50`; `Banana`, `3`, `0.75`) and confirm the receipt shows correct subtotals and total (`$5.25`).
- Test with invalid price (`abc`) and verify the error message.
- Test with negative quantity (`-1`) and confirm the error.
- Test with empty items (enter `done` immediately) and verify the “No items” message.
- Confirm both f-string and `format()` receipts match.

---

## Assessment Criteria
- **Correctness**: The script collects inputs, validates prices and quantities, and formats receipts accurately.
- **Clarity**: Code is commented, and the receipt is neatly formatted with aligned text and 2-decimal prices.
- **Completeness**: Handles errors, supports both f-strings and `format()`, and calculates totals correctly.

**Common Pitfalls**:
- Forgetting alignment (`{:<20}`) or decimal formatting (`{:.2f}`), causing messy output.
- Not handling invalid inputs, leading to crashes.
- Mismatching `format()` placeholder names.

---

## Extension Ideas
- **Discount Feature**: Apply a 10% discount if the total exceeds $100.
- **Save to File**: Write the receipt to a text file using `open()` and `write()`.
- **Table Formatting**: Use fixed-width columns for a more professional layout.

---

## Completion Checklist
- [ ] The script collects and validates item names, quantities, and prices.
- [ ] Generates a receipt with f-strings, showing aligned items and a total.
- [ ] Offers a `format()`-based receipt that matches the f-string output.
- [ ] Handles errors (non-numeric prices, non-positive quantities) with `ValueError`.
- [ ] Tested with valid and invalid inputs, confirming correct outputs and errors.
- [ ] Uses `{:<20}` and `{:.2f}` for formatting.

**One-Line Takeaway**: The Receipt Generator Tool uses f-strings and `format()` to create neatly formatted receipts, validating inputs to ensure robust and user-friendly operation.