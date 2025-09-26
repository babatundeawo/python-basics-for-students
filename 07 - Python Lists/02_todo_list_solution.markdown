# Solution to Simple To-Do List Manager Exercise

## Explanation

This solution implements a basic to-do list manager in Python, designed for beginners. It demonstrates key list operations like creating a list, appending items, checking for existence with `in`, removing items, and printing the list. The program starts with an initial list of tasks, prompts the user to add a new one, displays the list, then allows removal of a completed task after verifying it exists to prevent errors. This mirrors real-world task management and reinforces practical use of lists and user input.

The code is structured step by step:
1. Initialize the list with sample tasks.
2. Use `input()` to get a new task and `append()` to add it.
3. Print the list using `print()`.
4. Use `input()` again for a completed task, check if it's in the list with `in`, and remove it with `remove()` if present.
5. Print the updated list.

This approach builds confidence by showing how lists can be dynamically modified based on user interaction.

## Code Solution

```python
# Step 1: Create the initial to-do list
todo_list = ["Buy groceries", "Do homework", "Call friend"]

# Step 2: Ask user for a new task and append it
new_task = input("Enter a new task: ")
todo_list.append(new_task)

# Step 3: Print the current list
print("Current to-do list:")
print(todo_list)

# Step 4: Ask user for a completed task and remove it if it exists
completed_task = input("Enter a completed task to remove: ")
if completed_task in todo_list:
    todo_list.remove(completed_task)
    print("Task removed successfully.")
else:
    print("Task not found in the list.")

# Step 5: Print the updated list
print("Updated to-do list:")
print(todo_list)
```

## How to Run It
- Run the script in a Python environment.
- When prompted, enter a new task (e.g., "Clean room").
- Then, enter a task to remove (must match exactly, case-sensitive).
- Observe the list updates in the output.

This exercise helps beginners see lists in action for everyday problems, paving the way for more complex programs.