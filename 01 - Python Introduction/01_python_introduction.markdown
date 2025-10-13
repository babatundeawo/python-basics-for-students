# Python Introduction for Beginners

This tutorial introduces Python, a versatile programming language, focusing on its syntax, variables, comments, and basic execution. Below is a beginner-friendly teaching package designed to guide learners toward intermediate-level mastery with practical examples and exercises.

---

## Section 1 — Topical Explanations

### Learning Goals
- Understand what Python is and its common uses.
- Learn how to execute Python code via the command line or a file.
- Master basic Python syntax, including indentation, variables, and comments.
- Recognize common mistakes and how to fix them.

### What is Python?
Python is a popular, easy-to-read programming language created by Guido van Rossum in 1991. It’s widely used for:
- **Web development** (e.g., building server-side applications).
- **Software development** (e.g., creating apps or workflows).
- **Mathematics and data analysis** (e.g., handling big data or complex calculations).
- **System scripting** (e.g., automating tasks).

Python’s strengths include:
- **Cross-platform compatibility** (works on Windows, Mac, Linux, etc.).
- **Simple syntax**, resembling plain English, making it beginner-friendly.
- **Interpreted execution**, allowing code to run immediately without compilation.
- **Versatility**, supporting procedural, object-oriented, and functional programming.

Think of Python as a Swiss Army knife for programming—it’s flexible, powerful, and easy to carry across different tasks!

### Python Installation and Setup
Before writing Python code, ensure Python is installed:
1. **Check if Python is installed**:
   - On Windows: Open Command Prompt and type `python --version`.
   - On Mac/Linux: Open Terminal and type `python --version` or `python3 --version`.
   - Expected output: `Python 3.x.x` (e.g., `Python 3.9.1`).
2. If not installed, download it from [python.org](https://www.python.org/).

**Common Mistake**: Using `python` instead of `python3` on Mac/Linux, or vice versa. If one doesn’t work, try the other.  
**Fix**: Check the version with both commands or ensure the correct version is installed.

### Executing Python Code
Python code can be run in two ways:
1. **Command Line** (Interactive Mode):
   - Open Command Prompt/Terminal and type `python` or `py`.
   - Enter code directly, e.g., `print("Hello, World!")`.
   - Output appears immediately: `Hello, World!`.
   - Exit with `exit()`.
2. **Python File**:
   - Create a file (e.g., `hello.py`) in a text editor.
   - Write code, save, and run it via the command line: `python hello.py`.

**Example Code** (Running in a file):
```python
# hello.py
print("Hello, World!")  # Outputs the text "Hello, World!" to the console
```
- **Line-by-Line Explanation**:
  - `print()`: A built-in Python function that displays text or values.
  - `"Hello, World!"`: A string (text) passed as input to `print()`.
  - Output: `Hello, World!` appears on the screen.
  - No side effects; the code simply displays the text.
- **Visual Description**: When you run `python hello.py`, the terminal shows `Hello, World!` on a new line.
- **Common Mistake**: Saving the file with the wrong extension (e.g., `hello.txt` instead of `hello.py`).  
**Fix**: Ensure the file ends with `.py` and run it with `python filename.py`.
- **Validation Check**: Run the code. If you see `Hello, World!`, it worked! If not, check the file name or Python installation.

### Python Syntax: Indentation
Python uses **indentation** (spaces or tabs) to define blocks of code, unlike other languages that use curly braces `{}` or semicolons `;`. Indentation is critical for Python to understand the scope of loops, functions, or conditionals.

**Example Code**:
```python
if 5 > 2:  # Condition: checks if 5 is greater than 2
    print("Five is greater than two!")  # Indented line belongs to the if block
```
- **Line-by-Line Explanation**:
  - `if 5 > 2:`: Checks if 5 is greater than 2 (true). The colon `:` signals a new block.
  - `print("Five is greater than two!")`: Indented with 4 spaces, this line runs only if the condition is true.
  - Output: `Five is greater than two!`.
  - No side effects; it only prints text.
- **Visual Description**: The output appears in the terminal as a single line of text.
- **Common Mistake**: Forgetting indentation or using inconsistent spaces (e.g., mixing 2 and 4 spaces).  
  - **Error Example**:
    ```python
    if 5 > 2:
    print("Five is greater than two!")  # No indentation, causes SyntaxError
    ```
  - **Fix**: Add 4 spaces (or one tab, though spaces are preferred) before the `print` statement.
- **Validation Check**: Run the code. If it prints the message, indentation is correct. If you get a `SyntaxError`, check for missing or uneven indentation.

**Tip**: Use 4 spaces for indentation (standard in Python). Always be consistent within a block.

### Python Variables
Variables store data (like numbers or text) and are created by assigning a value using `=`. No special declaration is needed.

**Example Code**:
```python
x = 5  # Assigns the number 5 to variable x
y = "Hello, World!"  # Assigns the string "Hello, World!" to variable y
print(x)  # Outputs: 5
print(y)  # Outputs: Hello, World!
```
- **Line-by-Line Explanation**:
  - `x = 5`: Creates variable `x` and assigns it the integer `5`. Input: none. Output: none (just stores the value).
  - `y = "Hello, World!"`: Creates variable `y` and assigns it the string `"Hello, World!"`.
  - `print(x)`: Displays the value of `x` (5).
  - `print(y)`: Displays the value of `y` (`Hello, World!`).
  - No side effects; the code only stores and displays values.
- **Visual Description**: Running this code shows `5` on one line and `Hello, World!` on the next in the terminal.
- **Common Mistake**: Using invalid variable names (e.g., starting with a number or using special characters like `$`).  
  - **Error Example**: `$x = 5` or `1x = 5` causes a `SyntaxError`.  
  - **Fix**: Use letters, numbers, or underscores, starting with a letter or underscore (e.g., `x`, `my_var`).
- **Validation Check**: Add `print(x)` after `x = 5`. If it prints `5`, the variable is set correctly.

**Exercise Question**:
> What is the correct way to declare a Python variable?  
- Options: `var x = 5`, `#x = 5`, `$x = 5`, `x = 5`  
- **Answer**: `x = 5`  
  - Why? Python variables are created with a simple assignment (`name = value`). The others are incorrect:  
    - `var x = 5`: JavaScript-like syntax, not Python.  
    - `#x = 5`: A comment, ignored by Python.  
    - `$x = 5`: Invalid due to the `$` symbol.

### Python Comments
Comments explain code or prevent execution. They start with `#` (single-line) or use triple quotes `"""` for multiline comments.

**Example Code**:
```python
# This is a single-line comment
print("Hello, World!")  # Prints a greeting

"""
This is a multiline comment.
It can span multiple lines.
Ignored by Python unless assigned to a variable.
"""
x = 10  # Assigns 10 to x
# print(x)  # Commented out, won’t run
print("Done!")
```
- **Line-by-Line Explanation**:
  - `# This is a single-line comment`: Ignored by Python; used for clarity.
  - `print("Hello, World!")`: Outputs `Hello, World!`. The inline comment `# Prints a greeting` is ignored.
  - `"""..."""`: A multiline comment, ignored since it’s not assigned to a variable.
  - `x = 10`: Assigns `10` to `x`.
  - `# print(x)`: Commented out, so it doesn’t run.
  - `print("Done!")`: Outputs `Done!`.
  - Output: `Hello, World!` and `Done!` on separate lines.
  - No side effects beyond printing.
- **Visual Description**: The terminal shows `Hello, World!` and `Done!`, ignoring commented lines.
- **Common Mistake**: Forgetting the `#` or closing `"""` for multiline comments.  
  - **Error Example**: `This is a comment` (no `#` or `"""`) causes a `SyntaxError`.  
  - **Fix**: Add `#` for single-line or `"""` for multiline comments.
- **Validation Check**: Comment out a `print` statement. If it doesn’t appear in the output, the comment worked.

**One-Line Takeaway**: Python is an easy-to-learn, versatile language where indentation defines code blocks, variables are created by assignment, and comments clarify or disable code.

---

## Section 2 — Class Exercise

### Exercise: Create and Test a Simple Python Program

**Objective**: Write a Python program that uses variables, comments, and proper indentation to display a personalized greeting.

**Step-by-Step Instructions**:
1. Create a file named `greeting.py`.
2. Declare two variables:
   - `name` (a string with your name, e.g., `"Alice"`).
   - `age` (an integer with your age, e.g., `25`).
3. Use an `if` statement to check if `age` is greater than or equal to 18.
4. If true, print a message like: `Hello, [name]! You are an adult.`
5. If false, print: `Hello, [name]! You are not yet an adult.`
6. Add at least one single-line comment and one multiline comment to explain your code.
7. Run the program with `python greeting.py`.

**Hints**:
- Use 4 spaces for indentation under the `if` block.
- Remember the colon `:` after the `if` condition.
- Use `print()` to display the message.

**Checkpoint**:
- After running, check the output. Does it match your `age` condition?
- If you get a `SyntaxError`, check indentation or missing colons.

**Example Output** (for `name = "Alice"`, `age = 20`):
```
Hello, Alice! You are an adult.
```

---

## Section 3 — Weekly Project

### Project: Personal Info Card Generator

**Objective**: Create a Python program that collects user information and displays a formatted "info card" using variables, conditionals, and comments.

**Milestones**:
1. Create a file named `info_card.py`.
2. Declare variables for:
   - `first_name` (string, e.g., `"John"`).
   - `last_name` (string, e.g., `"Doe"`).
   - `age` (integer, e.g., `30`).
   - `occupation` (string, e.g., `"Student"`).
3. Use an `if` statement to determine if the user is a minor (`age < 18`).
4. Print a formatted card with:
   - Full name (combine `first_name` and `last_name`).
   - Age and whether they’re a minor or adult.
   - Occupation.
5. Add comments to explain each section.

**Deliverables**:
- A working `info_card.py` file.
- Output in the terminal showing the formatted card.

**Research Prompts**:
- How can you combine two strings (e.g., `first_name` and `last_name`) into one?
- What happens if you forget indentation in an `if` block?

**Assessment Criteria**:
- Code runs without errors.
- Variables are correctly assigned.
- Indentation is consistent (4 spaces).
- Comments explain the purpose of each section.
- Output is clear and includes all required info.

**Extension Idea**:
- Add a variable for `hobby` and include it in the card.
- Use a second `if` statement to print a special message if `age` is exactly 18.

**Example Output** (for `first_name = "John"`, `last_name = "Doe"`, `age = 30`, `occupation = "Student"`):
```
Personal Info Card
----------------
Name: John Doe
Age: 30 (Adult)
Occupation: Student
```

---

## Completion Checklist
- [ ] Understood Python’s uses (web development, data analysis, etc.).
- [ ] Installed Python and verified the version (`python --version`).
- [ ] Ran a simple program (`print("Hello, World!")`) in the command line and a `.py` file.
- [ ] Wrote code with proper indentation (4 spaces) in an `if` statement.
- [ ] Created variables using correct syntax (e.g., `x = 5`).
- [ ] Added single-line (`#`) and multiline (`"""`) comments.
- [ ] Completed the class exercise and verified the output.
- [ ] Started the weekly project and planned the info card layout.
- [ ] Identified and fixed at least one common mistake (e.g., indentation or invalid variable name).