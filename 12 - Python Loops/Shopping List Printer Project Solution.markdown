# **Solution to Weekly Project: Creating a Simple Shopping List Printer**

This document provides the solution to the weekly project from the Python loops lesson, specifically the **Creating a Simple Shopping List Printer** problem. The project requires using a **for loop** to iterate through a grocery list, print each item’s position and pair it with a category, skip the item “milk” using the `continue` statement, and print a completion message using the `else` statement. Below is the solution with an explanation tailored for complete beginners.

---

## **Explanation**

The goal is to create a program that prints a grocery list with item positions (e.g., “Item 1”) and categories (e.g., “Fruit: apple”), skips “milk” because it’s already been bought, and prints a completion message. We use a **for loop** with `range()` to iterate through the list and track indices, as this allows us to print item positions starting from 1. Here’s how the solution works:

1. **Define Lists**: Create a list of grocery items (including “milk”) and a list of categories.
2. **Set Up the For Loop**: Use `range(len(grocery_list))` to iterate through the indices of the grocery list, enabling us to print item numbers (e.g., “Item 1”).
3. **Skip “Milk”**: Check if the current item is “milk” and use `continue` to skip it.
4. **Assign Categories**: Pair each item with a category. For simplicity, we assign a single category (e.g., “Fruit”) to all items, but we note how to extend this with a nested loop or modulo for cycling categories.
5. **Print Item Details**: For each valid item, print its position (index + 1) and the item paired with a category.
6. **Completion Message**: Use the `else` block to print “Grocery list complete!” when the loop finishes.
7. **Curiosity Spark**: The project encourages exploring the `break` statement, but we stick to the core requirements here (skipping “milk” and printing all other items).

**Key Concepts Used**:
- **For Loop with `range()`**: Iterates through the list with indices to track item positions.
- **Continue Statement**: Skips the item “milk.”
- **Else Statement**: Runs when the loop completes normally, indicating the list is fully processed.
- **Lists**: Store grocery items and categories.
- **String Formatting**: Creates clear output like “Item 1: Fruit: apple.”

**Expected Output**:
```
Item 1: Fruit: apple
Item 3: Fruit: bread
Item 4: Fruit: banana
Grocery list complete!
```

---

## **Solution Code**

```python
grocery_list = ["apple", "milk", "bread", "banana"]
categories = ["Fruit", "Dairy", "Bakery"]

for i in range(len(grocery_list)):
    if grocery_list[i] == "milk":
        continue
    print(f"Item {i + 1}: {categories[0]}: {grocery_list[i]}")
else:
    print("Grocery list complete!")
```

---

## **Step-by-Step Walkthrough**

1. **Define Lists**:
   - `grocery_list = ["apple", "milk", "bread", "banana"]`: A list of 4 grocery items, including “milk” to be skipped.
   - `categories = ["Fruit", "Dairy", "Bakery"]`: A list of categories. For simplicity, we use the first category (“Fruit”) for all items.

2. **Set Up the For Loop**:
   - `for i in range(len(grocery_list))`: Iterates through indices `0` to `3` (since `len(grocery_list)` is 4).
   - Using `range(len(grocery_list))` allows us to access both the index (`i`) and the item (`grocery_list[i]`) while enabling position numbering.

3. **Skip “Milk”**:
   - `if grocery_list[i] == "milk": continue`: Checks if the current item is “milk.” If true, `continue` skips the rest of the loop body for that iteration.

4. **Print Item Details**:
   - `print(f"Item {i + 1}: {categories[0]}: {grocery_list[i]}")`: Prints the item’s position (`i + 1` to start at 1), the category (using `categories[0]`, i.e., “Fruit”), and the item name.
   - Example: For `i = 0`, prints “Item 1: Fruit: apple.”

5. **Else Block**:
   - `else: print("Grocery list complete!")`: Runs when the loop completes (i.e., after iterating through all indices), as long as the loop isn’t stopped by a `break`.

6. **Category Assignment**:
   - For simplicity, we use `categories[0]` (“Fruit”) for all items. This keeps the code beginner-friendly.
   - **Advanced Option** (not implemented but noted for curiosity): To cycle through categories, you could use `categories[i % len(categories)]` to map items to categories in a repeating pattern (e.g., “Fruit: apple,” “Dairy: milk,” “Bakery: bread,” “Fruit: banana”).

---

## **Why This Works**

- The `range(len(grocery_list))` approach allows us to track item positions (e.g., “Item 1”) while accessing list elements via `grocery_list[i]`.
- The `continue` statement ensures “milk” is skipped, so it doesn’t appear in the output.
- The `else` block confirms the loop’s completion, providing a clear end to the task.
- Using a single category (“Fruit”) simplifies the code for beginners while meeting the project’s requirements.
- The code uses only concepts from the **for loop** section (lists, `range()`, `continue`, `else`), making it accessible and directly tied to the lesson.

**Extending the Project**:
- To match categories more dynamically (e.g., “Dairy: milk,” “Bakery: bread”), you could use a nested loop or a dictionary (not covered in the lesson but a hint for future learning).
- To explore the curiosity spark, you could add a `break` statement (e.g., stop at “bread”) and observe how it affects the `else` block (it won’t run if `break` is used).

This solution is simple, meets all project requirements, and is beginner-friendly, focusing on the core **for loop** concepts from the lesson.