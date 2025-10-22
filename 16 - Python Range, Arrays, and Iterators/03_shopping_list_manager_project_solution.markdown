# Solution to Shopping List Manager Project

This document provides a solution to the **Shopping List Manager** project from the Python Range, Arrays (Lists), and Iterators teaching package. It includes the complete code, a detailed explanation, and verification of the expected functionality to help beginners understand and implement the project.

---

## Project Overview

**Objective:**\
Create a Python program that uses `range`, lists (as arrays), and iterators to manage a shopping list. Users can add items, view items with numbered positions, filter items by position, and review items one at a time interactively.

**Milestones:**

1. **Input Items:** Prompt the user to input item names until they type "done". Store items in a list.
2. **Display with Range:** Use `range()` to display the list with numbered positions (e.g., "1. apple").
3. **Filter by Position:** Use a list to store items at even-numbered positions (0-based index) using `range()`.
4. **Iterator Review:** Create an iterator to review items one at a time, stopping when the user chooses.

**Deliverables:**

- A Python script that implements all milestones.
- Comments explaining each part of the code.
- The program should run without errors and meet the assessment criteria.

**Expected Functionality:**

- Collects and stores items in a list.
- Displays items with numbered positions using `range()`.
- Filters items at even indices (0, 2, 4, etc.).
- Uses an iterator to review items interactively, allowing the user to stop early.

---

## Solution Code

```python
# Shopping List Manager
# This program manages a shopping list using range, lists, and iterators.

# Milestone 1: Input Items
def input_items():
    """Collects item names from the user until 'done' is entered."""
    items = []
    while True:
        item = input("Enter item name (or 'done' to finish): ")
        if item.lower() == 'done':
            break
        if item.strip():  # Ensure non-empty input
            items.append(item)
        else:
            print("Item name cannot be empty. Try again.")
    return items

# Milestone 2: Display with Range
def display_items(items):
    """Displays items with numbered positions using range."""
    if not items:
        print("No items in the list.")
        return
    print("\nShopping List:")
    for i in range(len(items)):
        print(f"{i + 1}. {items[i]}")

# Milestone 3: Filter by Position
def filter_even_positions(items):
    """Filters items at even-numbered positions (0-based index)."""
    return [items[i] for i in range(0, len(items), 2)]

# Milestone 4: Iterator Review
def review_items(items):
    """Uses an iterator to review items one at a time."""
    item_iterator = iter(items)
    print("\nReviewing items one at a time (press Enter to see next, 'q' to quit):")
    while True:
        try:
            item = next(item_iterator)
            print(f"Item: {item}")
            if input().lower() == 'q':
                break
        except StopIteration:
            print("No more items to review.")
            break

# Main Program
def main():
    print("Welcome to the Shopping List Manager!")
    
    # Milestone 1: Collect items
    items = input_items()
    if not items:
        print("No items added. Exiting.")
        return
    
    # Milestone 2: Display items with numbers
    display_items(items)
    
    # Milestone 3: Filter items at even positions
    even_position_items = filter_even_positions(items)
    print("\nItems at even-numbered positions (0-based index):")
    if even_position_items:
        for i, item in enumerate(even_position_items):
            print(f"Position {i * 2}: {item}")
    else:
        print("No items at even positions.")
    
    # Milestone 4: Review items with iterator
    review_items(items)

if __name__ == "__main__":
    main()
```

---

## Explanation

### Milestone 1: Input Items

**Code Breakdown:**

- **Function**: `input_items()`
- **Purpose**: Collects item names from the user until "done" is entered, storing them in a list.
- **Key Lines**:
  - `while True`: Loops until the user types "done".
  - `item = input(...)`: Gets the item name.
  - `if item.lower() == 'done'`: Breaks the loop when "done" is entered.
  - `if item.strip()`: Checks for non-empty input to avoid blank items.
  - `items.append(item)`: Adds valid items to the list.
  - `return items`: Returns the list of items.

**Why It Works:**

- The function handles user input robustly by checking for empty strings.
- It stores items in a list, which is mutable and suitable for dynamic additions.

**Common Pitfalls and Fixes:**

- **Pitfall**: Accepting empty inputs (e.g., pressing Enter without typing).
  - **Fix**: The `item.strip()` check ensures non-empty input.
- **Pitfall**: Case sensitivity in "done".
  - **Fix**: Use `item.lower()` for case-insensitive comparison.

**Validation Check:**

- Input: `apple`, `banana`, `orange`, `done` → Returns `["apple", "banana", "orange"]`.

### Milestone 2: Display with Range

**Code Breakdown:**

- **Function**: `display_items(items)`
- **Purpose**: Displays each item with a numbered position (1-based for user-friendliness) using `range()`.
- **Key Lines**:
  - `if not items`: Handles the empty list case.
  - `for i in range(len(items))`: Uses `range()` to generate indices 0 to `len(items)-1`.
  - `print(f"{i + 1}. {items[i]}")`: Prints each item with a 1-based number (e.g., "1. apple").

**Why It Works:**

- `range(len(items))` provides indices to access each item.
- Adding 1 to `i` makes the display user-friendly (1-based instead of 0-based).
- The empty list check prevents unnecessary output.

**Common Pitfalls and Fixes:**

- **Pitfall**: Accessing indices beyond the list length.
  - **Fix**: `range(len(items))` ensures valid indices.
- **Pitfall**: Using 0-based indexing for user display.
  - **Fix**: Add 1 to `i` for 1-based numbering.

**Validation Check:**

- For `["apple", "banana", "orange"]`, outputs:

  ```
  Shopping List:
  1. apple
  2. banana
  3. orange
  ```

### Milestone 3: Filter by Position

**Code Breakdown:**

- **Function**: `filter_even_positions(items)`
- **Purpose**: Returns a list of items at even-numbered positions (0-based indices: 0, 2, 4, etc.) using `range()`.
- **Key Lines**:
  - `range(0, len(items), 2)`: Generates even indices (0, 2, 4, ...).
  - `[items[i] for i in range(0, len(items), 2)]`: Creates a list of items at those indices.

**Why It Works:**

- The `range(0, len(items), 2)` efficiently selects even indices.
- The list comprehension builds the filtered list concisely.

**Common Pitfalls and Fixes:**

- **Pitfall**: Incorrect step size (e.g., `range(0, len(items), 1)` selects all items).
  - **Fix**: Use step `2` to get even indices.
- **Pitfall**: Empty list causing issues.
  - **Fix**: The function handles empty lists by returning an empty list.

**Validation Check:**

- For `["apple", "banana", "orange", "grape"]`, returns `["apple", "orange"]` (indices 0 and 2).

### Milestone 4: Iterator Review

**Code Breakdown:**

- **Function**: `review_items(items)`
- **Purpose**: Uses an iterator to display items one at a time, allowing the user to stop early.
- **Key Lines**:
  - `item_iterator = iter(items)`: Creates an iterator from the list.
  - `while True`: Loops until exhausted or user quits.
  - `item = next(item_iterator)`: Gets the next item.
  - `try ... except StopIteration`: Handles the end of iteration.
  - `if input().lower() == 'q'`: Allows the user to quit by entering 'q'.

**Why It Works:**

- The iterator yields items one at a time, making it memory-efficient.
- The `try-except` block gracefully handles the end of the list.
- User interaction with 'q' to quit makes it flexible.

**Common Pitfalls and Fixes:**

- **Pitfall**: Not handling `StopIteration`.
  - **Fix**: The `except StopIteration` block stops the loop.
- **Pitfall**: Printing the iterator directly (shows an iterator object).
  - **Fix**: Use `next()` to access items.

**Validation Check:**

- For `["apple", "banana"]`, displays each item one at a time, stopping if the user enters 'q' or the list ends.

### Main Program

**Code Breakdown:**

- **Function**: `main()`
- **Purpose**: Orchestrates the program flow, calling each function and displaying results.
- **Key Steps**:
  - Calls `input_items()` to collect the shopping list.
  - Uses `display_items()` to show numbered items.
  - Calls `filter_even_positions()` to show items at even indices.
  - Uses `review_items()` for interactive review with an iterator.

**Sample Run:**

```
Welcome to the Shopping List Manager!
Enter item name (or 'done' to finish): apple
Enter item name (or 'done' to finish): banana
Enter item name (or 'done' to finish): orange
Enter item name (or 'done' to finish): grape
Enter item name (or 'done' to finish): done

Shopping List:
1. apple
2. banana
3. orange
4. grape

Items at even-numbered positions (0-based index):
Position 0: apple
Position 2: orange

Reviewing items one at a time (press Enter to see next, 'q' to quit):
Item: apple

Item: banana
q
```

---

## Assessment Criteria Check

- **Collects and stores items**: `input_items()` stores items in a list.
- **Displays numbered items**: `display_items()` uses `range()` for 1-based numbering.
- **Filters even indices**: `filter_even_positions()` correctly selects items at indices 0, 2, 4, etc.
- **Iterator review**: `review_items()` uses an iterator for interactive review.
- **Error-free and commented**: The code runs without errors and includes clear comments.

---

## Completion Checklist

- [ ] Implemented `input_items()` to collect and store items.

- [ ] Wrote `display_items()` to show numbered items using `range()`.

- [ ] Created `filter_even_positions()` to filter items at even indices.

- [ ] Built `review_items()` to review items with an iterator.

- [ ] Integrated all parts in `main()` with user-friendly output.

- [ ] Included comments explaining each function.

- [ ] Avoided pitfalls like invalid indices or missing `StopIteration`.

**One-Line Takeaway:**\
The Shopping List Manager uses `range`, lists, and iterators to efficiently collect, display, filter, and review shopping items interactively.