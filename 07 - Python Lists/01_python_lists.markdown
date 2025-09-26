# Python Lists Tutorial

## Section 1 – Explanations

### Python Lists Overview

Lists in Python are used to store multiple items in a single variable. They are one of Python’s four built-in collection data types (alongside Tuples, Sets, and Dictionaries). Lists are versatile because they are **ordered**, **changeable**, and **allow duplicates**. This means items in a list maintain their position, can be modified after creation, and can include repeated values.

### Key Concepts of Lists

1. **Creating a List**  
   Lists are created using square brackets `[]` or the `list()` constructor. For example:
   ```python
   mylist = ["apple", "banana", "cherry"]
   print(mylist)  # Output: ['apple', 'banana', 'cherry']
   ```
   The `list() constructor can also create a list from an iterable like a tuple:
   ```python
   thislist = list(("apple", "banana", "cherry"))
   print(thislist)  # Output: ['apple', 'banana', 'cherry']
   ```

2. **List Items**  
   - **Ordered**: Items have a fixed order, and new items are added to the end unless specified otherwise.
   - **Changeable**: You can modify, add, or remove items after the list is created.
   - **Allow Duplicates**: Lists can contain multiple identical items:
     ```python
     thislist = ["apple", "banana", "apple"]
     print(thislist)  # Output: ['apple', 'banana', 'apple']
     ```

3. **Accessing List Items**  
   List items are indexed starting at `0` for the first item. You can access items using their index:
   ```python
   thislist = ["apple", "banana", "cherry"]
   print(thislist[1])  # Output: banana
   ```
   - **Negative Indexing**: Start from the end with `-1` for the last item:
     ```python
     print(thislist[-1])  # Output: cherry
     ```
   - **Range of Indexes**: Use slicing to access a range of items, e.g., `thislist[1:3]` returns items from index 1 to (but not including) index 3:
     ```python
     thislist = ["apple", "banana", "cherry", "orange"]
     print(thislist[1:3])  # Output: ['banana', 'cherry']
     ```

4. **Modifying Lists**  
   - **Change Items**: Update an item by its index:
     ```python
     thislist = ["apple", "banana", "cherry"]
     thislist[1] = "orange"
     print(thislist)  # Output: ['apple', 'orange', 'cherry']
     ```
   - **Insert Items**: Use `insert()` to add an item at a specific index:
     ```python
     thislist.insert(1, "kiwi")
     print(thislist)  # Output: ['apple', 'kiwi', 'orange', 'cherry']
     ```
   - **Append Items**: Use `append()` to add an item to the end:
     ```python
     thislist.append("mango")
     print(thislist)  # Output: ['apple', 'kiwi', 'orange', 'cherry', 'mango']
     ```
   - **Extend Lists**: Use `extend()` to add multiple items from another iterable:
     ```python
     thislist.extend(["grape", "pear"])
     print(thislist)  # Output: ['apple', 'kiwi', 'orange', 'cherry', 'mango', 'grape', 'pear']
     ```

5. **Removing Items**  
   - **Remove Specific Item**: Use `remove()` to delete the first occurrence of an item:
     ```python
     thislist.remove("kiwi")
     print(thislist)  # Output: ['apple', 'orange', 'cherry', 'mango', 'grape', 'pear']
     ```
   - **Remove by Index**: Use `pop()` to remove an item at a specific index (or the last item if no index is provided):
     ```python
     thislist.pop(1)
     print(thislist)  # Output: ['apple', 'cherry', 'mango', 'grape', 'pear']
     ```
   - **Clear List**: Use `clear()` to empty the list:
     ```python
     thislist.clear()
     print(thislist)  # Output: []
     ```

6. **Looping Through Lists**  
   You can iterate over a list using a `for` loop:
   ```python
   thislist = ["apple", "banana", "cherry"]
   for fruit in thislist:
       print(fruit)
   # Output:
   # apple
   # banana
   # cherry
   ```
   Alternatively, loop using indices with `range()` and `len()`:
   ```python
   for i in range(len(thislist)):
       print(thislist[i])
   ```

7. **List Comprehension**  
   List comprehension provides a concise way to create a new list based on an existing one, preserving the old list:
   ```python
   fruits = ["apple", "banana", "cherry", "kiwi", "mango"]
   newlist = [x for x in fruits if "a" in x]
   print(newlist)  # Output: ['apple', 'banana', 'mango']
   ```

8. **Sorting and Copying**  
   - **Sort**: Use `sort()` to sort the list alphanumerically:
     ```python
     thislist = ["orange", "apple", "banana"]
     thislist.sort()
     print(thislist)  # Output: ['apple', 'banana', 'orange']
     ```
   - **Copy**: Use `copy()`, `list()`, or slicing `[:]` to create a copy of a list to avoid modifying the original:
     ```python
     mylist = ["apple", "banana"]
     newlist = mylist.copy()
     newlist.append("cherry")
     print(mylist)  # Output: ['apple', 'banana']
     print(newlist)  # Output: ['apple', 'banana', 'cherry']
     ```

### Why Lists Matter  
Lists are a foundational tool in Python because they allow you to store and manipulate multiple pieces of data efficiently. Understanding lists builds the skills needed to work with more complex data structures later.

## Section 2 – Class Exercise

### Exercise: Build a Simple To-Do List Manager

This exercise reinforces list creation, appending, removing, and accessing items by having you create a basic to-do list manager.

**Steps:**
1. Create a list called `todo_list` with three initial tasks (e.g., "Buy groceries", "Do homework", "Call friend").
2. Ask the user to input a new task and append it to the list.
3. Print the entire list to show all tasks.
4. Ask the user to input a task they’ve completed, then remove it from the list.
5. Print the updated list.

**Guidance:**
- Use `input()` to get user input for the new task and the completed task.
- Use `append()` to add the new task to the list.
- Use `remove()` to delete the completed task.
- Use a `for` loop or simple `print()` to display the list.
- Hint: Make sure the task entered for removal exists in the list to avoid errors (use `in` to check).

This exercise mirrors a real-world scenario of managing tasks and helps you practice basic list operations.

## Section 3 – Weekly Project

### Weekly Project: Create a Shopping List Organizer

This project combines lists, user input, loops, and list methods to create a practical tool that could be expanded in future lessons.

**Project Brief:**
Build a program that helps a user manage a shopping list. The program should:
1. Start with an empty list called `shopping_list`.
2. Allow the user to add items to the list until they type "done".
3. Display the full list in alphabetical order.
4. Allow the user to remove one item they’ve purchased.
5. Show the updated list.

**Milestones:**
1. Create an empty list: `shopping_list = []`.
2. Use a `while` loop to repeatedly ask for items with `input()` until the user types "done".
3. Sort the list using `sort()`.
4. Print the sorted list using a `for` loop.
5. Ask for an item to remove using `input()` and remove it with `remove()` (check if it exists using `in`).
6. Print the updated list.

**Encouragement for Creativity:**
- Try adding a feature to categorize items (e.g., "food", "household") to hint at future dictionary use.
- Consider displaying the list with item numbers (use `range()` and `len()` in a loop).
- Think about how you might save the list for later (hinting at file handling in future lessons).

This project reinforces list operations and builds confidence in creating a useful tool, setting the stage for learning more advanced concepts like loops with conditions or data persistence.