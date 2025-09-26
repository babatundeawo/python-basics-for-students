# **Python Sets: Market Stall Inventory Tracker – Code Solution and Explanation**

This document provides the code solution for the **Market Stall Inventory Tracker** weekly project from the Python Sets lesson, tailored for Nigerian beginners as per the Nigeria-Focused AI Instructional Framework. The project involves creating a program to manage unique items in two market stalls (e.g., in Mile 12 Market) using Python sets, incorporating user input and set operations like `union()`, `intersection()`, and `difference()`. Below, the solution is presented first, followed by a detailed explanation of each part, ensuring clarity and relatability with Nigerian-themed context.

---

## **Code Solution**

```python
# Create two sets for market stalls
stall1 = {"yam", "tomato", "fish"}
stall2 = {"tomato", "pepper", "onion"}

# Step 1: Combine inventories using union
all_items = stall1.union(stall2)
print(f"All unique items from both stalls: {all_items}")

# Step 2: Find common items using intersection
common_items = stall1.intersection(stall2)
print(f"Items sold by both stalls: {common_items}")

# Step 3: Find items unique to each stall using difference
unique_to_stall1 = stall1.difference(stall2)
unique_to_stall2 = stall2.difference(stall1)
print(f"Items unique to Stall 1: {unique_to_stall1}")
print(f"Items unique to Stall 2: {unique_to_stall2}")

# Step 4: Add a new item to stall1
new_item = input("Enter a new item to add to Stall 1: ")
stall1.add(new_item)
print(f"Stall 1 after adding {new_item}: {stall1}")

# Step 5: Remove an item from stall2
remove_item = input("Enter an item to remove from Stall 2: ")
stall2.discard(remove_item)
print(f"Stall 2 after removing {remove_item}: {stall2}")

# Step 6: Display final inventories
print(f"Final Stall 1 inventory: {stall1}")
print(f"Final Stall 2 inventory: {stall2}")
```

**Sample Output** (order may vary due to sets being unordered; example assumes user inputs "plantain" to add and "pepper" to remove):
```
All unique items from both stalls: {'yam', 'tomato', 'fish', 'pepper', 'onion'}
Items sold by both stalls: {'tomato'}
Items unique to Stall 1: {'yam', 'fish'}
Items unique to Stall 2: {'pepper', 'onion'}
Enter a new item to add to Stall 1: plantain
Stall 1 after adding plantain: {'yam', 'tomato', 'fish', 'plantain'}
Enter an item to remove from Stall 2: pepper
Stall 2 after removing pepper: {'tomato', 'onion'}
Final Stall 1 inventory: {'yam', 'tomato', 'fish', 'plantain'}
Final Stall 2 inventory: {'tomato', 'onion'}
```

---

## **Explanation**

This section explains each part of the code solution step-by-step, tying it to Nigerian experiences to make it clear and engaging for beginners. The explanation follows the framework’s guidelines: simple language, progressive steps, and confidence-building examples.

### **Step 1: Creating Two Sets**
```python
stall1 = {"yam", "tomato", "fish"}
stall2 = {"tomato", "pepper", "onion"}
```
- **What it does**: Creates two sets, `stall1` and `stall2`, representing the inventories of two market stalls in Mile 12 Market. Each set contains unique items, with "tomato" as a common item.
- **Why it’s a set**: Sets use curly brackets `{}` and automatically prevent duplicates, ensuring each stall’s inventory lists each item only once (e.g., no two "yams" in `stall1`).
- **Relatable analogy**: This is like writing down the unique goods each trader sells in their stall, similar to listing items like "rice" or "beans" on a market board without repeating them.

### **Step 2: Combining Inventories Using `union()`**
```python
all_items = stall1.union(stall2)
print(f"All unique items from both stalls: {all_items}")
```
- **What it does**: Uses the `union()` method to combine all unique items from `stall1` and `stall2` into a new set, `all_items`, and prints it.
- **How it works**: `union()` takes all items from both sets, removing any duplicates (e.g., "tomato" appears only once in the result). The output might be `{'yam', 'tomato', 'fish', 'pepper', 'onion'}` (order varies).
- **Relatable analogy**: This is like combining the goods from two stalls to create a single list of everything available at a market, similar to telling customers all the food items they can buy from both traders.

### **Step 3: Finding Common Items Using `intersection()`**
```python
common_items = stall1.intersection(stall2)
print(f"Items sold by both stalls: {common_items}")
```
- **What it does**: Uses the `intersection()` method to find items present in both `stall1` and `stall2`, storing them in `common_items`, and prints the result (e.g., `{'tomato'}`).
- **How it works**: `intersection()` keeps only the items that appear in both sets, like finding the overlap between two market stalls’ offerings.
- **Relatable analogy**: This is like checking which items two traders both sell, such as discovering that both have tomatoes, similar to finding common snacks at two school canteens.

### **Step 4: Finding Unique Items Using `difference()`**
```python
unique_to_stall1 = stall1.difference(stall2)
unique_to_stall2 = stall2.difference(stall1)
print(f"Items unique to Stall 1: {unique_to_stall1}")
print(f"Items unique to Stall 2: {unique_to_stall2}")
```
- **What it does**: Uses the `difference()` method to find items in `stall1` that aren’t in `stall2` (stored in `unique_to_stall1`) and vice versa (stored in `unique_to_stall2`), then prints both.
- **How it works**: `stall1.difference(stall2)` returns items in `stall1` not in `stall2` (e.g., `{'yam', 'fish'}`), and `stall2.difference(stall1)` returns items in `stall2` not in `stall1` (e.g., `{'pepper', 'onion'}`).
- **Relatable analogy**: This is like identifying which items are exclusive to each trader’s stall, similar to finding out which stall sells unique goods like yam that the other doesn’t.

### **Step 5: Adding a New Item to `stall1`**
```python
new_item = input("Enter a new item to add to Stall 1: ")
stall1.add(new_item)
print(f"Stall 1 after adding {new_item}: {stall1}")
```
- **What it does**: Uses `input()` to prompt the user to enter a new item (e.g., "plantain"), adds it to `stall1` using `add()`, and prints the updated set.
- **How it works**: `input()` gets a string from the user, and `add()` includes it in `stall1`. If the item is already in the set (e.g., "yam"), it won’t be added again due to the no-duplicates rule.
- **Relatable analogy**: This is like a trader adding a new item to their stall, such as bringing in plantains after a customer request, similar to updating a shop’s inventory.

### **Step 6: Removing an Item from `stall2`**
```python
remove_item = input("Enter an item to remove from Stall 2: ")
stall2.discard(remove_item)
print(f"Stall 2 after removing {remove_item}: {stall2}")
```
- **What it does**: Prompts the user to enter an item to remove from `stall2` (e.g., "pepper"), uses `discard()` to remove it, and prints the updated set.
- **Why use `discard()`?**: `discard()` safely removes the item without raising an error if it’s not in the set, making it beginner-friendly.
- **Relatable analogy**: This is like a trader removing an item they no longer sell, such as taking pepper off the stall because it’s sold out, similar to updating a market display.

### **Step 7: Displaying Final Inventories**
```python
print(f"Final Stall 1 inventory: {stall1}")
print(f"Final Stall 2 inventory: {stall2}")
```
- **What it does**: Prints the final contents of `stall1` and `stall2` after all operations.
- **How it works**: The `print()` function displays the updated sets, showing the results of adding and removing items (e.g., `stall1` might be `{'yam', 'tomato', 'fish', 'plantain'}` and `stall2` might be `{'tomato', 'onion'}`).
- **Relatable analogy**: This is like showing customers the final list of goods available at each stall, similar to displaying a shop’s updated stock list.

### **Why This Program Builds Confidence**
- **Practical and relatable**: Managing market stall inventories feels like running a real business in Mile 12 Market, something Nigerian students can relate to and share with friends.
- **Showcases set features**: The code demonstrates key set operations (`union()`, `intersection()`, `difference()`, `add()`, `discard()`) and user input, reinforcing the lesson’s concepts in a practical way.
- **Encourages experimentation**: Students can try adding or removing different items or creating new stalls, building confidence in their Python skills and sparking pride in their work.

---

This solution and explanation provide a complete, beginner-friendly guide to the Market Stall Inventory Tracker project. The code is simple, uses Nigerian market-themed items to make it relatable, and demonstrates set operations in a way that students can proudly share with peers, sparking conversations like “I built a market inventory tracker with Python!”