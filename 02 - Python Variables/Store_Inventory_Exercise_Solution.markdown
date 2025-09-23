# Solution to Class Exercise: Track a Small Store’s Inventory

## Explanation

The exercise requires creating a Python program to track a small store’s inventory by storing three product names and their prices, displaying them, and calculating the total price. The solution uses variables to store strings (product names) and numbers (prices), and the `print()` function with commas to output the information clearly. The total price is calculated using the `+` operator. The solution employs **snake_case** for variable names to enhance readability, as recommended for multi-word variables.

The steps are:
1. Create variables for three product names (strings).
2. Create variables for their prices (floats for decimal precision).
3. Use `print()` with commas to display each product and its price.
4. Calculate and print the total price by adding the price variables.

This approach ensures the code is beginner-friendly, avoids type mismatch errors by using commas in `print()`, and follows variable naming rules.

## Solution Code

```python
# Step 1: Create variables for product names
item_1 = "Apple"
item_2 = "Banana"
item_3 = "Orange"

# Step 2: Create variables for prices
price_1 = 0.5
price_2 = 0.75
price_3 = 1.0

# Step 3: Print each product and its price
print("Item:", item_1, "Price:", price_1)
print("Item:", item_2, "Price:", price_2)
print("Item:", item_3, "Price:", price_3)

# Step 4: Calculate and print the total price
total_price = price_1 + price_2 + price_3
print("Total Price:", total_price)
```

## Explanation of the Code

- **Variable Creation**: 
  - `item_1`, `item_2`, `item_3` are assigned string values ("Apple", "Banana", "Orange") to represent product names.
  - `price_1`, `price_2`, `price_3` are assigned float values (0.5, 0.75, 1.0) to represent prices, allowing for decimal points common in pricing.
  - Snake_case (`item_1`, `price_1`) is used for clear, readable variable names.

- **Output with `print()`**:
  - The `print()` function uses commas to combine strings and numbers (e.g., `print("Item:", item_1, "Price:", price_1)`). This avoids errors that would occur if using `+` to concatenate strings with numbers.
  - Each print statement outputs a product and its price in a readable format (e.g., `Item: Apple Price: 0.5`).

- **Total Price Calculation**:
  - The `total_price` variable is created by adding `price_1`, `price_2`, and `price_3` using the `+` operator, which performs mathematical addition for numbers.
  - The total is printed with a descriptive label using `print("Total Price:", total_price)`.

## Expected Output

When you run the code, it will produce:

```
Item: Apple Price: 0.5
Item: Banana Price: 0.75
Item: Orange Price: 1.0
Total Price: 2.25
```

This output is clear, matches the exercise requirements, and demonstrates proper use of variables, output formatting, and basic arithmetic for beginners.