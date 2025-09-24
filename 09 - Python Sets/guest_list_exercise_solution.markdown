# **Solution to Class Exercise: Managing a Guest List**

This document provides the solution to the class exercise on managing a guest list using Python sets, as outlined in the Python Sets lesson. The exercise is designed for complete beginners, and the solution includes explanations for each step to reinforce understanding of sets, their properties, and basic operations. The goal is to create a guest list, ensure no duplicates, check for specific guests, add new guests, and remove one, all while using Python sets.

---

## **Explanation and Solution**

The exercise involves creating a guest list for a party using a Python set to ensure no duplicate names, checking if a specific person is invited, adding new guests from a list, and removing a guest. Below is the step-by-step solution with explanations for each part, followed by the complete code.

### **Step 1: Create a set called `guests` with three names**
We create a set named `guests` with the names "Alice", "Bob", and "Charlie". Sets are defined using curly brackets `{}` and automatically ensure no duplicates. Since these names are unique, the set will contain all three.

### **Step 2: Print the initial guest list**
We print the `guests` set to display the initial list. Since sets are unordered, the names may appear in any order when printed.

### **Step 3: Check if "Bob" is in the guest list**
We use the `in` keyword to check if "Bob" is in the `guests` set. This will return `True` because "Bob" is one of the initial names.

### **Step 4: Add a new guest, "Diana"**
We use the `add()` method to add "Diana" to the `guests` set. This method adds a single item to the set, and since "Diana" is not already present, it will be included.

### **Step 5: Create a list called `new_guests` with two names**
We create a list named `new_guests` containing "Eve" and "Bob". Note that "Bob" is already in the `guests` set, so it will be ignored when added to avoid duplicates.

### **Step 6: Add the `new_guests` list to the `guests` set**
We use the `update()` method to add all items from the `new_guests` list to the `guests` set. The `update()` method accepts any iterable (like a list) and adds its elements to the set, ignoring duplicates. Thus, "Eve" will be added, but "Bob" will not create a duplicate.

### **Step 7: Print the updated guest list and its length**
We print the updated `guests` set to show all guests after adding "Diana" and "Eve". We also use the `len()` function to display the number of unique guests, which should be 4 (Alice, Bob, Charlie, Diana, Eve).

### **Step 8: Remove "Charlie" and print the final guest list**
We use the `discard()` method to remove "Charlie" from the `guests` set. The `discard()` method is safe because it does not raise an error if the item is not found. We then print the final guest list, which should contain "Alice", "Bob", "Diana", and "Eve".

### **Complete Solution Code**
Below is the complete Python code that implements the above steps.

```python
# Step 1: Create a set with three names
guests = {"Alice", "Bob", "Charlie"}

# Step 2: Print the initial guest list
print("Initial guest list:", guests)

# Step 3: Check if "Bob" is in the guest list
print("Is Bob invited?", "Bob" in guests)

# Step 4: Add "Diana" to the guest list
guests.add("Diana")

# Step 5: Create a list with two names
new_guests = ["Eve", "Bob"]

# Step 6: Add the new_guests list to the guests set
guests.update(new_guests)

# Step 7: Print the updated guest list and its length
print("Updated guest list:", guests)
print("Number of guests:", len(guests))

# Step 8: Remove "Charlie" and print the final guest list
guests.discard("Charlie")
print("Final guest list:", guests)
```

### **Expected Output**
Running the above code will produce output similar to the following (note that the order of items in a set may vary due to its unordered nature):

```
Initial guest list: {'Alice', 'Bob', 'Charlie'}
Is Bob invited? True
Updated guest list: {'Alice', 'Bob', 'Charlie', 'Diana', 'Eve'}
Number of guests: 5
Final guest list: {'Alice', 'Bob', 'Diana', 'Eve'}
```

### **Explanation of Key Concepts**
- **Sets and No Duplicates**: When we added "Bob" from the `new_guests` list, it was ignored because "Bob" was already in the `guests` set, demonstrating that sets automatically handle duplicates.
- **Unordered Nature**: The printed sets may show items in different orders each time, as sets do not maintain a specific order.
- **Using `add()` and `update()`**: The `add()` method is for single items, while `update()` handles multiple items from any iterable, making it versatile for adding from lists or other sets.
- **Using `discard()`**: We chose `discard()` over `remove()` to safely remove "Charlie" without risking an error if "Charlie" were not in the set.
- **Using `len()`**: The `len()` function counts unique items, which is useful for tracking the total number of guests.
- **Using `in`**: The `in` keyword provides a simple way to check for the presence of an item, which is efficient for sets.

### **Why This Matters**
This exercise simulates a real-world scenario where you need to maintain a unique list (e.g., party guests, event attendees, or unique product IDs). Sets are ideal for such tasks because they ensure no duplicates and provide efficient methods for adding, removing, and checking items. This builds confidence in using sets for simple collection management tasks.