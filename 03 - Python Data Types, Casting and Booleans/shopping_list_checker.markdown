# **Solution to Shopping List Checker Exercise**

This document provides the solution to the "Shopping List Checker" exercise from the Python Data Types lesson. The exercise involves creating a program to check items on a shopping list by storing an item’s name (string), quantity (integer), and price (float), then performing type checking, casting, and a boolean check for stock availability. Below, I’ll explain the solution step-by-step and provide the complete code, ensuring it’s clear for complete beginners.

## **Explanation**

The exercise requires us to:
1. Store an item’s name, quantity, and price with appropriate data types.
2. Use `type()` to display each variable’s data type.
3. Cast the quantity to a float and the price to a string, then print them.
4. Check if the item is in stock (quantity > 0) and print the boolean result.
5. Use `isinstance()` to verify if the price is a float.

### **Step-by-Step Explanation**
1. **Creating Variables**:
   - We define `item_name` as a string (e.g., "milk"), `quantity` as an integer (e.g., 3), and `price` as a float (e.g., 2.99). These data types align with the lesson’s focus on `str`, `int`, and `float`.

2. **Checking Data Types**:
   - We use the `type()` function to print the data type of each variable. This helps confirm that Python assigned the correct types based on the values.

3. **Casting Variables**:
   - We convert `quantity` to a float using `float()` (e.g., 3 becomes 3.0).
   - We convert `price` to a string using `str()` (e.g., 2.99 becomes "2.99").
   - These demonstrate casting, as covered in the lesson.

4. **Boolean Check for Stock**:
   - We use a comparison (`quantity > 0`) to create a boolean value indicating if the item is in stock. This uses the lesson’s concept of booleans from comparisons.

5. **Verifying Data Type with `isinstance()`**:
   - We use `isinstance(price, float)` to check if `price` is a float, reinforcing the lesson’s use of `isinstance()` for type checking.

### **Solution Code**
Below is the complete Python code that solves the exercise, producing output that matches the example format provided in the exercise.

```python
# Step 1: Create variables for item name, quantity, and price
item_name = "milk"
quantity = 3
price = 2.99

# Step 2: Print the data type of each variable
print("Item type:", type(item_name))
print("Quantity type:", type(quantity))
print("Price type:", type(price))

# Step 3: Cast quantity to float and price to string, then print
quantity_float = float(quantity)
price_string = str(price)
print("Quantity as float:", quantity_float)
print("Price as string:", price_string)

# Step 4: Check if item is in stock (quantity > 0)
in_stock = quantity > 0
print("Is item in stock?", in_stock)

# Step 5: Check if price is a float using isinstance()
is_price_float = isinstance(price, float)
print("Is price a float?", is_price_float)
```

### **Expected Output**
When you run the code, it will produce:
```
Item type: <class 'str'>
Quantity type: <class 'int'>
Price type: <class 'float'>
Quantity as float: 3.0
Price as string: 2.99
Is item in stock? True
Is price a float? True
```

### **How It Works**
- **Variables**: `item_name = "milk"` is a string, `quantity = 3` is an integer, and `price = 2.99` is a float.
- **Type Checking**: `type()` shows the data types as `<class 'str'>`, `<class 'int'>`, and `<class 'float'>`.
- **Casting**: `float(quantity)` converts 3 to 3.0, and `str(price)` converts 2.99 to "2.99".
- **Boolean Check**: `quantity > 0` evaluates to `True` since 3 is greater than 0.
- **Type Verification**: `isinstance(price, float)` returns `True` because `price` is a float.

This solution uses only the concepts from the lesson (data types, casting, booleans, and `isinstance()`), keeping it simple and beginner-friendly. You can try changing the values (e.g., `quantity = 0` or `price = 5`) to see how the output changes, especially for the stock check!