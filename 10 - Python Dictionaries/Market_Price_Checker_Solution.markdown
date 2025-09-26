# **Solution to the Market Price Checker Exercise (Nigeria-Focused Edition)**

This document provides the code solution to the **Market Price Checker** class exercise from the Python Dictionaries lesson, along with a detailed explanation tailored for Nigerian beginners. The solution adheres to the Nigeria-focused instructional framework, ensuring it is clear, relatable, and beginner-friendly. The explanation follows the same structure as the original lesson response, focusing on the exercise's concepts and code.

---

## **Section 1 – Explanations**

This section explains the solution to the **Market Price Checker** exercise, breaking down the code step-by-step with Nigerian-themed examples. The exercise involves creating a program that:
1. Stores at least three items and their prices in a dictionary.
2. Asks the user to input an item name.
3. Checks if the item exists and prints its price, or displays "Item not found."
4. Allows the user to update the price of an item and displays the updated dictionary.

### **Solution Code**
Below is the complete Python code for the Market Price Checker:

```python
# Create a dictionary with market items and their prices
market = {
    "Rice": 2500,
    "Beans": 3000,
    "Yam": 1500
}

# Print the initial market inventory
print("Market Inventory:", market)

# Ask user for an item to check its price
item_name = input("Enter item name to check price (e.g., Rice, Beans, Yam): ")

# Check if the item exists and display its price
if item_name in market:
    print(f"The price of {item_name} is ₦{market[item_name]}")
else:
    print("Item not found.")

# Ask user if they want to update a price
update_choice = input("Do you want to update a price? (yes/no): ")

if update_choice.lower() == "yes":
    # Get item name and new price
    item_to_update = input("Enter item name to update (e.g., Rice, Beans, Yam): ")
    new_price = int(input("Enter new price (in ₦): "))
    
    # Update the price in the dictionary
    market[item_to_update] = new_price
    print("Updated Market Inventory:", market)
else:
    print("No changes made to the inventory.")
```

### **Line-by-Line Explanation**

This code uses dictionaries, `input()`, conditionals (`if-else`), and string formatting, all relatable to a Nigerian market context. Below is a detailed breakdown:

1. **Creating the Dictionary**:
   ```python
   market = {
       "Rice": 2500,
       "Beans": 3000,
       "Yam": 1500
   }
   ```
   - Creates a dictionary called `market` with three key:value pairs, where keys are item names (e.g., `"Rice"`) and values are prices in naira (e.g., `2500`).
   - **Relatable Analogy**: This is like a trader at Balogun Market writing down the prices of goods on a list, where each item has a specific price.

2. **Printing the Initial Inventory**:
   ```python
   print("Market Inventory:", market)
   ```
   - Displays the entire dictionary to show the user the current stock and prices.
   - Output example: `Market Inventory: {'Rice': 2500, 'Beans': 3000, 'Yam': 1500}`.
   - It’s like showing a customer the full price list before they ask for a specific item.

3. **Getting User Input for Item Name**:
   ```python
   item_name = input("Enter item name to check price (e.g., Rice, Beans, Yam): ")
   ```
   - Uses `input()` to ask the user to type an item name and stores it in `item_name`.
   - **Relatable Analogy**: This is like a customer asking a trader, “How much is Rice?” at a market stall.

4. **Checking if the Item Exists**:
   ```python
   if item_name in market:
       print(f"The price of {item_name} is ₦{market[item_name]}")
   else:
       print("Item not found.")
   ```
   - Uses the `in` keyword to check if `item_name` is a key in the `market` dictionary.
   - If the item exists, it prints the price using `market[item_name]` (e.g., `"The price of Rice is ₦2500"`).
   - If the item doesn’t exist, it prints `"Item not found."`.
   - **Relatable Analogy**: This is like a trader checking their price list. If the item is listed, they tell the customer the price; if not, they say it’s not available.

5. **Asking to Update a Price**:
   ```python
   update_choice = input("Do you want to update a price? (yes/no): ")
   ```
   - Asks the user if they want to update a price and stores their response (`"yes"` or `"no"`) in `update_choice`.
   - **Relatable Analogy**: This is like a trader deciding whether to change the price of an item due to market changes (e.g., fuel price increase affecting rice prices).

6. **Handling the Update Choice**:
   ```python
   if update_choice.lower() == "yes":
   ```
   - Converts the user’s input to lowercase (`.lower()`) to handle inputs like `"Yes"`, `"YES"`, or `"yes"`.
   - Checks if the user wants to update a price by comparing with `"yes"`.
   - **Relatable Analogy**: This ensures the trader understands the customer’s request, even if they say “YES” or “yes.”

7. **Getting Item and New Price for Update**:
   ```python
   item_to_update = input("Enter item name to update (e.g., Rice, Beans, Yam): ")
   new_price = int(input("Enter new price (in ₦): "))
   ```
   - Asks for the item to update and the new price.
   - Converts the price input to an integer using `int()` to store it as a number.
   - **Relatable Analogy**: This is like a trader asking, “Which item’s price do you want to change, and to how much?” (e.g., “Rice to ₦3000”).

8. **Updating the Dictionary**:
   ```python
   market[item_to_update] = new_price
   print("Updated Market Inventory:", market)
   ```
   - Updates the price of the specified item in the `market` dictionary.
   - Prints the updated dictionary to show the changes.
   - Example: If the user updates `"Rice"` to `3000`, the dictionary becomes `{'Rice': 3000, 'Beans': 3000, 'Yam': 1500}`.
   - **Relatable Analogy**: This is like the trader updating their price list and showing the new list to confirm the change.

9. **Handling No Update**:
   ```python
   else:
       print("No changes made to the inventory.")
   ```
   - If the user chooses not to update (`"no"`), prints a message indicating no changes.
   - **Relatable Analogy**: This is like the trader saying, “Okay, I’ll keep the prices as they are.”

### **Why It’s Beginner-Friendly**
- The code uses simple dictionary operations (`in`, key access, assignment) and basic conditionals (`if-else`), which are accessible to beginners.
- It incorporates `input()` to make the program interactive, like a real market interaction.
- The Nigerian market context (e.g., Rice, Beans, Yam) makes it relatable, and the program feels like a practical tool a trader could use.

### **Confidence-Building**
- Students can run this program and see it work like a real market price checker, which they can proudly show to friends, saying, “I built a program to check prices at a market stall!”
- The program is small but functional, showing how dictionaries can solve real-world problems, like managing a shop’s inventory.

### **Sample Output**
```
Market Inventory: {'Rice': 2500, 'Beans': 3000, 'Yam': 1500}
Enter item name to check price (e.g., Rice, Beans, Yam): Rice
The price of Rice is ₦2500
Do you want to update a price? (yes/no): yes
Enter item name to update (e.g., Rice, Beans, Yam): Rice
Enter new price (in ₦): 3000
Updated Market Inventory: {'Rice': 3000, 'Beans': 3000, 'Yam': 1500}
```

**Alternative Scenario**:
```
Market Inventory: {'Rice': 2500, 'Beans': 3000, 'Yam': 1500}
Enter item name to check price (e.g., Rice, Beans, Yam): Garri
Item not found.
Do you want to update a price? (yes/no): no
No changes made to the inventory.
```

---

This solution and explanation cover the exercise comprehensively, using a Nigerian market context to make it engaging and relatable. Students can use this as a reference to understand dictionaries while building something practical and boast-worthy.