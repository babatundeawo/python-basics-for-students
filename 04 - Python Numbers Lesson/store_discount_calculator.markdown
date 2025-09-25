# Solution to the Store Discount Calculator Exercise

Below is the solution to the **Class Exercise: Build a Simple Calculator for a Store Discount** from the Python Numbers lesson, written in Markdown with an explanation tailored for complete beginners. The exercise involves creating a program that calculates the final price of an item after applying a discount, using integers, floats, and basic arithmetic.

## Explanation

The goal of this exercise is to create a program that:
- Takes user input for the original price of an item (a number with decimals, like 19.99).
- Takes user input for a discount percentage (a whole number, like 10 for 10%).
- Calculates the discount amount using the formula: `discount_amount = original_price * (discount_percentage / 100)`.
- Calculates the final price: `final_price = original_price - discount_amount`.
- Displays the discount amount and final price, rounded to two decimal places for clarity.

### Step-by-Step Breakdown
1. **Getting User Input**:
   - We use `float(input())` to get the original price because prices often have decimals (e.g., $19.99).
   - We use `int(input())` for the discount percentage because percentages are typically whole numbers (e.g., 10%).
   - The `input()` function returns a string, so we convert it to the appropriate numeric type (`float` or `int`).

2. **Calculating the Discount**:
   - To calculate the discount amount, multiply the original price by the discount percentage divided by 100. For example, a 10% discount on $20 is `$20 * (10 / 100) = $2`.
   - This ensures the discount is proportional to the price.

3. **Calculating the Final Price**:
   - Subtract the discount amount from the original price to get the final price.
   - For example, if the original price is $20 and the discount is $2, the final price is `$20 - $2 = $18`.

4. **Rounding for Readability**:
   - Prices are typically shown with two decimal places (e.g., $18.00). We use the `round(number, 2)` function to ensure this.

5. **Displaying Results**:
   - Use `print()` to show the discount amount and final price in a clear, readable sentence.
   - We include the variable values in the output to make it user-friendly.

This program uses **floats** for decimal calculations and an **integer** for the percentage, reinforcing the numeric types from the lesson. It’s a practical example of how numbers are used in real-world scenarios like shopping.

## Solution Code

```python
# Get the original price from the user (a number with decimals)
original_price = float(input("Enter the original price of the item: $"))

# Get the discount percentage from the user (a whole number)
discount_percentage = int(input("Enter the discount percentage (e.g., 10 for 10%): "))

# Calculate the discount amount
discount_amount = original_price * (discount_percentage / 100)

# Calculate the final price
final_price = original_price - discount_amount

# Display the results, rounded to 2 decimal places
print("The discount is", round(discount_amount, 2), "dollars, and the final price is", round(final_price, 2), "dollars.")
```

## How It Works
- If the user enters `19.99` for the original price and `10` for the discount percentage:
  - The discount amount is `19.99 * (10 / 100) = 1.999`, which rounds to `2.00`.
  - The final price is `19.99 - 1.999 = 17.991`, which rounds to `17.99`.
  - The output will be: `The discount is 2.0 dollars, and the final price is 17.99 dollars.`
- The program handles decimals accurately using floats and ensures the output is clean and professional with rounding.

## Why This Matters
This exercise shows how to:
- Use `float` and `int` types for different kinds of numbers.
- Perform basic arithmetic operations (multiplication, division, subtraction).
- Use `input()` to interact with users.
- Format output to make it clear and useful.
This is a foundation for more complex programs, like budgeting tools or shopping apps, and it builds confidence in handling numbers in Python.