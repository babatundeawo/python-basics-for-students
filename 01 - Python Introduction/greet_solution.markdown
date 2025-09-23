# **Solution to the Class Exercise: Create a Simple Greeting Program**

This document provides the solution to the class exercise from the Python Introduction lesson, which involves creating a program to greet customers visiting a store’s website. The exercise requires using variables, the `print()` function, and comments, with proper indentation. Below, I’ll explain the solution step-by-step and provide the complete code, ensuring it remains beginner-friendly and aligned with the lesson’s concepts.

## **Explanation of the Solution**

The exercise asks for a Python program (`greet.py`) that:
- Stores a customer’s name in a variable.
- Prints a welcome message using the name.
- Includes a single-line comment to explain the code.
- Runs correctly with proper syntax and indentation.

### **Key Concepts Used**
- **Variables**: We create a variable `name` to store the customer’s name as a string.
- **print() Function**: We use `print()` to display a message that includes the variable.
- **Comments**: We add a single-line comment to describe the purpose of the `print()` statement.
- **Indentation**: Since this program doesn’t use code blocks (e.g., `if` statements), no indentation is needed for the main code, ensuring simplicity.
- **Running the Program**: The code is saved as a `.py` file and executed via the command line (`python greet.py`).

### **Step-by-Step Breakdown**
1. **Create the File**: We create a file named `greet.py` in a text editor.
2. **Define the Variable**: Assign a string (e.g., "Alice") to a variable called `name`.
3. **Add a Comment**: Include a single-line comment (starting with `#`) above the `print()` statement to explain its purpose.
4. **Print the Message**: Use `print()` to output a welcome message, combining the string "Welcome to our store," with the `name` variable and an exclamation mark.
5. **Run the Program**: Save the file and run it in the command line to see the output: `Welcome to our store, Alice!`.

### **Solution Code**
Below is the complete code for `greet.py`, which meets all the exercise requirements:

```python
# File: greet.py
name = "Alice"  # Store the customer's name in a variable
# Print a personalized welcome message for the customer
print("Welcome to our store,", name, "!")
```

### **How It Works**
- `name = "Alice"`: Creates a variable `name` and assigns it the string `"Alice"`.
- `# Print a personalized welcome message for the customer`: A single-line comment explaining the next line.
- `print("Welcome to our store,", name, "!")`: Prints the message by combining a string, the `name` variable, and an exclamation mark. The commas in `print()` automatically add spaces between elements.
- **Output**: When run with `python greet.py`, the program outputs:
  ```
  Welcome to our store, Alice!
  ```

### **Testing and Variations**
- You can change the `name` variable to any string (e.g., `name = "Bob"`) and rerun the program to see a new output like `Welcome to our store, Bob!`.
- The code avoids indentation because it’s a simple sequence of statements, not inside a block (e.g., no `if` or loop).
- If an error occurs (e.g., incorrect file name or missing Python installation), ensure Python is installed (`python --version`) and the command is run in the correct directory.

### **Why This Works for Beginners**
- **Simplicity**: Uses only variables, `print()`, and a comment, directly from the lesson.
- **Real-World Context**: Mimics a website greeting, making it relatable.
- **Reinforces Concepts**: Practices variable assignment, commenting, and running Python files, building confidence for beginners.

This solution provides a clear, working program that fulfills the exercise requirements while staying within the scope of the Python Introduction lesson.