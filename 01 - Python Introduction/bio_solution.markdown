# **Solution to the Weekly Project: Personal Bio Generator**

This document provides the solution to the weekly project from the Python Introduction lesson, which involves creating a program (`bio.py`) for a school club’s website to introduce new members with a short bio. The project requires using variables, the `print()` function, single-line and multi-line comments, and proper indentation. Below, I’ll explain the solution step-by-step and provide the complete code, ensuring it remains beginner-friendly and aligned with the lesson’s concepts.

## **Explanation of the Solution**

The project asks for a Python program (`bio.py`) that:
- Stores a member’s name, age, and favorite hobby in variables.
- Prints a formatted bio, such as: "Meet [name]! They are [age] years old and enjoy [hobby]."
- Includes at least one single-line comment and one multi-line comment to explain the code.
- Uses proper indentation to ensure the code runs without errors.

### **Key Concepts Used**
- **Variables**: We create variables to store the member’s `name` (string), `age` (number), and `hobby` (string).
- **print() Function**: We use `print()` to display a formatted bio combining strings and variables.
- **Comments**: We include a multi-line comment (using triple quotes `"""`) at the top to describe the program’s purpose and a single-line comment (using `#`) before the `print()` statement to explain its role.
- **Indentation**: Since this program doesn’t involve code blocks (e.g., `if` statements or loops), no indentation is needed for the main code, keeping it simple.
- **Running the Program**: The code is saved as a `.py` file and executed via the command line (`python bio.py`).

### **Step-by-Step Breakdown**
1. **Create the File**: Create a file named `bio.py` in a text editor.
2. **Add a Multi-line Comment**: Start with a multi-line comment explaining the program’s purpose (e.g., generating a bio for a school club).
3. **Define Variables**: Assign values to three variables: `name` (e.g., "Sam"), `age` (e.g., 16), and `hobby` (e.g., "painting").
4. **Add a Single-line Comment**: Include a comment before the `print()` statement to describe what it outputs.
5. **Print the Bio**: Use `print()` to combine strings and variables into a formatted bio, ensuring proper spacing and punctuation.
6. **Run the Program**: Save the file and run it in the command line with `python bio.py` to see the output, e.g., `Meet Sam! They are 16 years old and enjoy painting.`.

### **Solution Code**
Below is the complete code for `bio.py`, which meets all the project requirements:

```python
# File: bio.py
"""
This program generates a short bio for a school club member.
It stores the member's name, age, and hobby in variables and
prints a formatted introduction for the club's website.
"""
name = "Sam"  # Member's name
age = 16      # Member's age
hobby = "painting"  # Member's favorite hobby
# Print a formatted bio for the club member
print("Meet", name, "! They are", age, "years old and enjoy", hobby, ".")
```

### **How It Works**
- `""" ... """`: A multi-line comment at the top explains the program’s purpose, ignored by Python.
- `name = "Sam"`, `age = 16`, `hobby = "painting"`: Assigns values to three variables to store the member’s details.
- `# Print a formatted bio for the club member`: A single-line comment explains the `print()` statement’s purpose.
- `print("Meet", name, "! They are", age, "years old and enjoy", hobby, ".")`: Combines strings and variables to output the bio. Commas in `print()` automatically add spaces between elements.
- **Output**: When run with `python bio.py`, the program outputs:
  ```
  Meet Sam! They are 16 years old and enjoy painting.
  ```

### **Testing and Variations**
- **Change Variables**: Modify `name`, `age`, or `hobby` (e.g., `name = "Maya"`, `age = 14`, `hobby = "soccer"`) and rerun to see a new bio, like `Meet Maya! They are 14 years old and enjoy soccer.`.
- **Indentation**: No indentation is needed since there are no code blocks, but consistency is maintained for readability.
- **Error Checking**: If the program doesn’t run, verify Python is installed (`python --version`), the file is saved as `bio.py`, and the command is run in the correct directory.
- **Exploration**: Try adding more variables (e.g., favorite color) or tweaking the bio’s wording for creativity, though keep it simple to stay within the lesson’s scope.

### **Why This Works for Beginners**
- **Simplicity**: Uses only variables, `print()`, and comments, directly from the lesson.
- **Real-World Context**: Mimics a club website bio, making it engaging and relatable.
- **Reinforces Concepts**: Practices variable assignment, commenting, and running Python files, while encouraging experimentation with output formatting.
- **Curiosity Spark**: Combining strings and variables hints at string concatenation or formatting (e.g., using `+` or f-strings), which future lessons may cover.

This solution provides a clear, working program that fulfills the project requirements, builds confidence, and sets the stage for learning more advanced Python concepts.