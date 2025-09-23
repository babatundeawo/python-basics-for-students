# **Python Introduction**

## **Section 1 – Explanations**

This lesson introduces Python, a versatile programming language created by Guido van Rossum and released in 1991. Below, I’ll explain the key concepts covered in the lesson, keeping it beginner-friendly and focused.

### **What is Python?**

Python is a popular programming language known for its simplicity and versatility. It is used for:

- **Web development** (server-side, e.g., creating web applications).
- **Software development** (building applications or workflows).
- **Mathematics** (performing complex calculations or handling big data).
- **System scripting** (automating tasks on a computer).

Python’s strengths include:

- **Cross-platform compatibility**: Works on Windows, Mac, Linux, Raspberry Pi, etc.
- **Simple syntax**: Reads like English, making it easier to learn.
- **Fewer lines of code**: Allows concise programming compared to other languages.
- **Interpreter-based**: Code runs immediately after being written, enabling quick prototyping.
- **Flexible programming styles**: Supports procedural, object-oriented, and functional programming.

### **Python Syntax**

Python’s syntax is designed for readability:

- **New lines** end a command (unlike semicolons in languages like C or Java).
- **Indentation** (spaces at the start of a line) defines code blocks, such as loops or functions, unlike curly brackets used in other languages.
- **Example**:

  ```python
  print("Hello, World!")
  ```

  This code prints "Hello, World!" to the screen. It’s simple and doesn’t require extra symbols like semicolons.

### **Python Installation and Running Code**

- Many computers come with Python pre-installed. To check, run `python --version` (or `py --version`) in the command line (Windows: `cmd.exe`, Linux/Mac: Terminal).
- If not installed, download Python from python.org.
- Python files (`.py`) are written in a text editor and executed via the command line:

  ```python
  # File: hello.py
  print("Hello, World!")
  ```

  Run it with: `python hello.py`, which outputs `Hello, World!`.
- You can also run Python interactively in the command line by typing `python` or `py`, then entering code like `print("Hello, World!")`.

### **Indentation**

Indentation is critical in Python, unlike other languages where it’s just for readability. It defines the scope of code blocks (e.g., after an `if` statement):

```python
if 5 > 2:
    print("Five is greater than two!")  # Indented with 4 spaces
```

- Skipping indentation or using inconsistent spaces (e.g., mixing 2 and 4 spaces) causes errors.
- Example of incorrect indentation:

  ```python
  if 5 > 2:
  print("Five is greater than two!")  # Error: Missing indentation
  ```

### **Variables**

Variables store data and are created by assigning a value:

```python
x = 5
y = "Hello, World!"
```

- No special command is needed to declare variables, unlike some other languages.
- Variables can hold numbers, text, or other data types.

### **Comments**

Comments explain code or prevent execution for testing:

- **Single-line comments** start with `#`:

  ```python
  # This is a comment
  print("Hello, World!")
  ```
- **Multi-line comments** can use multiple `#` lines or triple quotes (`"""`):

  ```python
  """
  This is a multi-line comment
  Ignored by Python
  """
  print("Hello, World!")
  ```
- Comments improve readability and can disable code (e.g., `#print("Test")`).

## **Section 2 – Class Exercise**

### **Exercise: Create a Simple Greeting Program**

**Real-world problem**: You’re building a program to greet customers visiting a store’s website. The program should print a welcome message and store the customer’s name in a variable.

**Step-by-step guidance**:

1. Create a file named `greet.py` in a text editor.
2. Define a variable `name` and assign it a string value (e.g., your name or a fictional customer’s name).
3. Use the `print()` function to display a message like "Welcome to our store, \[name\]!".
4. Add a single-line comment above the `print()` statement explaining what the code does.
5. Save the file and run it using the command line (`python greet.py`).
6. Check the output. If it doesn’t work, ensure your indentation is correct (use 4 spaces) and the file name is correct.

**Tips**:

- Use the `print()` syntax from the lesson.
- Ensure proper indentation (no spaces before the variable or `print()` unless inside a block).
- Test with different names by changing the variable’s value.

This exercise uses variables, the `print()` function, and comments, reinforcing the lesson’s concepts.

## **Section 3 – Weekly Project**

### **Project: Personal Bio Generator**

**Real-world scenario**: You’re creating a program for a school club’s website that introduces new members by printing a short bio based on their details.

**Project brief**: Write a Python program (`bio.py`) that:

- Stores a member’s name, age, and favorite hobby in variables.
- Prints a formatted bio, such as: "Meet \[name\]! They are \[age\] years old and enjoy \[hobby\]."
- Includes at least one single-line comment and one multi-line comment to explain your code.
- Uses proper indentation to ensure the code runs without errors.

**Step-by-step guidelines**:

1. Create a file named `bio.py` in a text editor.
2. Define three variables: `name` (string), `age` (number), and `hobby` (string).
3. Add a multi-line comment at the top of the file explaining the program’s purpose.
4. Add a single-line comment before the `print()` statement describing what it displays.
5. Use the `print()` function to output the bio. Hint: You can combine strings using commas in `print(name, "is", age, "years old")`.
6. Save and run the file using `python bio.py` in the command line.
7. Test your program by changing the variable values (e.g., different names or hobbies).

**Curiosity spark**:

- Try combining multiple strings and variables in a single `print()` statement. Can you make the output look polished (e.g., adding spaces or punctuation)?
- What happens if you try printing a number and a string together? This might hint at string concatenation or formatting, which you’ll explore in future lessons.

**Tips**:

- Keep indentation consistent (use 4 spaces for any code blocks, though this project likely won’t need them yet).
- Use the lesson’s examples for `print()`, variables, and comments as a guide.
- Be creative with the bio’s wording to make it fun!

This project combines variables, comments, and `print()` while encouraging experimentation with output formatting, setting the stage for learning about strings and concatenation later.