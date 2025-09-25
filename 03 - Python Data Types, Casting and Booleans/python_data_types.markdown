# Python Data Types for Complete Beginners

## Section 1 – Explanations

In Python, **data types** define the kind of information a variable can hold, like numbers, text, or lists. Each data type has specific uses and behaviors. Let’s break down the key concepts from the lesson, focusing on the most beginner-friendly data types: strings (`str`), integers (`int`), floats (`float`), booleans (`bool`), lists (`list`), and dictionaries (`dict`). We’ll also cover how to check data types with `type()` and convert between types using **casting**.

### 1. **Common Data Types**
- **String (`str`)**: Stores text, like names or sentences. Strings are enclosed in quotes (`" "` or `' '`).
  ```python
  name = "Amina"
  print(name)  # Outputs: Amina
  ```
  Strings can be anything from a single word to a full sentence. They’re like labeled boxes for words.

- **Integer (`int`)**: Stores whole numbers (no decimals), like 5 or -10.
  ```python
  age = 15
  print(age)  # Outputs: 15
  ```
  Integers are used for counting or quantities, like the number of apples.

- **Float (`float`)**: Stores numbers with decimals, like 3.14 or 0.5.
  ```python
  height = 1.75
  print(height)  # Outputs: 1.75
  ```
  Floats are useful for measurements or calculations needing precision.

- **Boolean (`bool`)**: Stores either `True` or `False`. Booleans are used to make decisions.
  ```python
  is_student = True
  print(is_student)  # Outputs: True
  ```
  Booleans often come from comparisons, like checking if 10 > 5 (which is `True`).

- **List (`list`)**: Stores a collection of items, like a shopping list. Lists are created with square brackets `[]`.
  ```python
  fruits = ["apple", "banana", "orange"]
  print(fruits)  # Outputs: ['apple', 'banana', 'orange']
  ```
  Lists can hold multiple data types (e.g., strings, numbers) and can be changed.

- **Dictionary (`dict`)**: Stores key-value pairs, like a phonebook where names (keys) map to numbers (values).
  ```python
  person = {"name": "John", "age": 36}
  print(person)  # Outputs: {'name': 'John', 'age': 36}
  ```
  Dictionaries are great for organizing related information.

### 2. **Checking Data Types with `type()`**
The `type()` function tells you the data type of a variable.
```python
x = 5
print(type(x))  # Outputs: <class 'int'>
y = "Hello"
print(type(y))  # Outputs: <class 'str'>
```
This is like asking Python, “What kind of box is this variable?” It’s super helpful for debugging or understanding your code.

### 3. **Casting: Changing Data Types**
Sometimes, you need to convert one data type to another. This is called **casting**, and it’s done with constructor functions like `int()`, `float()`, and `str()`.

- **Convert to Integer (`int()`)**:
  ```python
  x = int(2.8)  # Converts float 2.8 to integer 2 (drops decimals)
  y = int("3")  # Converts string "3" to integer 3
  print(x, y)  # Outputs: 2 3
  ```

- **Convert to Float (`float()`)**:
  ```python
  x = float(1)    # Converts integer 1 to float 1.0
  y = float("4.2")  # Converts string "4.2" to float 4.2
  print(x, y)  # Outputs: 1.0 4.2
  ```

- **Convert to String (`str()`)**:
  ```python
  x = str(5)    # Converts integer 5 to string "5"
  y = str(3.14) # Converts float 3.14 to string "3.14"
  print(x, y)  # Outputs: 5 3.14
  ```

Casting is like changing the label on a box to store a different kind of data. For example, turning a number into a string lets you combine it with text.

### 4. **Booleans in Detail**
Booleans (`True` or `False`) are often used in decision-making, like in `if` statements.
```python
a = 10
b = 5
print(a > b)  # Outputs: True (because 10 is greater than 5)
```
The `bool()` function can also evaluate values:
```python
print(bool("Hello"))  # Outputs: True (non-empty strings are True)
print(bool(0))        # Outputs: False (zero is False)
print(bool([]))       # Outputs: False (empty lists are False)
```
This is useful for checking if data exists (e.g., is a string empty?).

### Why This Matters
Understanding data types is like learning the building blocks of Python. Each type (strings, numbers, lists, etc.) lets you store and work with information in different ways. By combining them, you can create powerful programs, like a to-do list app or a budget tracker.

## Section 2 – Class Exercise

### Exercise: Build a “Personal Profile Creator”
Create a simple program that collects information about a person and displays it. This exercise reinforces data types, casting, and basic input/output.

**Steps:**
1. Ask the user for their name (a string).
2. Ask the user for their age (an integer).
3. Ask the user for their height in meters (a float).
4. Store these inputs in variables with appropriate data types.
5. Print a summary message, like: `"Hi, [name]! You are [age] years old and [height] meters tall."`
6. Use `type()` to print the data type of each variable to confirm they’re correct.

**Guidance:**
- Use `input()` to get user input (it returns a string).
- Cast the age input to an `int` using `int()` and the height input to a `float` using `float()`.
- Combine the inputs into a single `print()` statement using commas or string concatenation.
- Test your program with different inputs to ensure it works.

This exercise is practical because it mimics real-world forms, like signing up for an account. It uses strings, integers, floats, and casting, reinforcing the lesson’s concepts.

## Section 3 – Weekly Project

### Weekly Project: Create a “Student Grade Calculator”
Build a program that calculates and displays a student’s average grade, using data types and casting. This project combines the lesson’s concepts (strings, numbers, lists) with previously learned input/output.

**Project Brief:**
Your program should:
1. Ask the user for the student’s name (string).
2. Ask for three test scores (floats) and store them in a list.
3. Calculate the average score (a float) by summing the scores and dividing by 3.
4. Determine if the student passed (average >= 60) using a boolean.
5. Print a summary, like: `"[name]'s average score is [average]. Pass: [True/False]."`

**Milestones:**
1. Use `input()` to get the name and scores. Cast score inputs to `float()` to handle decimals.
2. Store scores in a list, e.g., `scores = [score1, score2, score3]`.
3. Calculate the average using `sum(scores) / len(scores)`.
4. Use an `if` statement to set a boolean variable (`passed`) based on the average.
5. Print the summary, ensuring all data types are used correctly (e.g., convert the average to a string for printing if needed).
6. **Bonus**: Add a feature to let the user enter the number of tests (e.g., 2 or 4 instead of 3), hinting at loops (a future topic).

**Guidance:**
- Start by collecting and storing the inputs.
- Test with different scores to ensure the average and pass/fail logic work.
- Use `type()` to verify your variables’ data types if you’re unsure.
- Be creative! You could add a message like “Great job!” for passing students.

This project is exciting because it mimics real-world grading systems and encourages you to combine data types creatively. It builds confidence by showing how simple inputs and calculations can produce useful results, while subtly introducing the idea of lists and conditionals for future lessons.