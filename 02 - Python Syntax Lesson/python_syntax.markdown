# Python Syntax Lesson

## Section 1 – Explanations

This lesson introduces foundational Python syntax concepts: executing Python code, indentation, variables, and comments. Below is an explanation of each concept, using the provided examples and adhering to beginner-friendly clarity.

### 1. Executing Python Syntax
Python code can be executed in two primary ways:
- **Command Line (Interactive Mode)**: You can type Python code directly into the command line (or terminal) and see immediate results. For example:
  ```python
  >>> print("Hello, World!")
  Hello, World!
  ```
  The `print()` function outputs text to the console.
- **Python File**: You can save code in a file with a `.py` extension (e.g., `myfile.py`) and run it using the command line with `python myfile.py`. This is useful for larger programs.

### 2. Python Indentation
Indentation refers to the spaces at the start of a code line and is critical in Python because it defines blocks of code (e.g., code under an `if` statement). Unlike other languages where indentation is optional for readability, Python requires it for functionality.
- Example:
  ```python
  if 5 > 2:
      print("Five is greater than two!")
  ```
  Here, the `print` statement is indented under the `if` condition, indicating it belongs to that block.
- **Rules for Indentation**:
  - Indentation must be consistent within a block (e.g., always use 4 spaces or 1 tab, though 4 spaces is standard).
  - Skipping indentation causes a syntax error:
    ```python
    if 5 > 2:
    print("Five is greater than two!")  # Error: missing indentation
    ```
  - Mixing different indentation levels (e.g., 2 spaces and 4 spaces) in the same block also causes an error:
    ```python
    if 5 > 2:
     print("Five is greater than two!")  # Error: inconsistent indentation
            print("Five is greater than two!")
    ```

### 3. Python Variables
Variables store data and are created when you assign a value to them using the `=` operator. Python does not require explicit variable declarations.
- Example:
  ```python
  x = 5
  y = "Hello, World!"
  ```
  Here, `x` stores the number `5`, and `y` stores the string `"Hello, World!"`. You can use these variables later in your code.

### 4. Python Comments
Comments are used to document code, improve readability, or prevent code execution during testing. They are ignored by Python when running the program.
- **Single-line Comments**: Start with `#`, and Python ignores the rest of the line.
  - Example:
    ```python
    #This is a comment
    print("Hello, World!")
    ```
    The comment does not affect the output: `Hello, World!`.
  - Comments can also appear at the end of a line:
    ```python
    print("Hello, World!")  #This is a comment
    ```
  - Comments can prevent code execution:
    ```python
    #print("Hello, World!")
    print("Cheers, Mate!")
    ```
    Output: `Cheers, Mate!` (the commented line is ignored).
- **Multiline Comments**: Python lacks a dedicated multiline comment syntax, but you can use:
  - Multiple `#` lines:
    ```python
    #This is a comment
    #written in
    #more than just one line
    print("Hello, World!")
    ```
  - A multiline string (triple quotes `"""` or `'''`) that is not assigned to a variable:
    ```python
    """
    This is a comment
    written in
    more than just one line
    """
    print("Hello, World!")
    ```
    Python ignores the unassigned string, treating it as a comment.

## Section 2 – Class Exercise

This lesson supports a beginner-friendly exercise to reinforce the concepts of executing code, indentation, variables, and comments.

### Exercise: Write and Run a Simple Python Program
Create a Python program that uses variables, proper indentation, and comments to display a greeting based on a condition.

**Step-by-Step Guidance**:
1. Create a new file named `greeting.py`.
2. Write a comment at the top explaining what the program does (e.g., `# This program checks a number and prints a greeting`).
3. Create a variable (e.g., `number`) and assign it a value between 1 and 10.
4. Use an `if` statement to check if the number is greater than 5.
5. Inside the `if` block, use proper indentation (4 spaces) to print a message like `"Number is large!"`.
6. Add a comment inside the `if` block explaining the condition.
7. Save the file and run it using the command line (`python greeting.py`).
8. Check the output and ensure there are no indentation errors.
9. Experiment by changing the variable’s value and observe how the output changes.

**Expected Outcome**: The program should print the message only if the condition is true, and it should run without syntax errors.

## Section 3 – Weekly Project

This lesson supports a simple project to practice the concepts of variables, indentation, and comments in a creative way.

### Project Brief: Personal Greeting Generator
Create a Python program that asks the user for their name, stores it in a variable, and uses an `if` statement to print a personalized greeting based on the length of the name. Use comments to explain your code.

**Step-by-Step Guidelines**:
1. Create a file named `personal_greeting.py`.
2. Add a multiline comment (using `"""`) at the start to describe the program’s purpose.
3. Use the `input()` function to ask the user for their name and store it in a variable (e.g., `name = input("Enter your name: ")`).
4. Use the `len()` function to get the length of the name (e.g., `name_length = len(name)`).
5. Write an `if` statement to check if the name length is greater than 5.
6. Inside the `if` block, print a greeting like `"Hello [name], you have a long name!"`. Use proper indentation.
7. Add a single-line comment inside the `if` block to explain the condition.
8. If the name is 5 characters or fewer, print a different greeting like `"Hello [name], short and sweet!"` in an `else` block (optional challenge).
9. Save and run the program using `python personal_greeting.py`.
10. Test with different names to ensure the program works as expected.

**Tips**:
- Use clear variable names (e.g., `name`, `name_length`).
- Ensure consistent indentation (4 spaces is standard).
- Add comments to explain each major step.
- Be creative with the greeting messages!

**Expected Outcome**: The program should take a name as input and print an appropriate greeting based on the name’s length, with clear comments and no syntax errors.