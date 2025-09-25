# Solution to the Personalized Greeting Program Exercise

This document provides the solution to the "Create a Personalized Greeting Program" exercise from the Python Introduction lesson, tailored for complete beginners. The exercise involves creating a Python program that uses variables, the `print()` function, and comments to display a personalized greeting. Below, I’ll explain the solution step-by-step and provide the complete code, following the instructional guide’s structure for clarity and beginner-friendliness.

---

## Explanation

The exercise asks you to create a Python file called `greeting.py` that:
- Stores your name in a variable called `my_name`.
- Stores your favorite number in a variable called `fav_number`.
- Uses the `print()` function to display a message like: "Hello, my name is [your name] and my favorite number is [your number]."
- Includes comments to explain each line of code.

### Key Concepts Used
- **Variables**: These are used to store data, like your name (a string, which is text in quotes) and your favorite number (an integer, which is a whole number). Variables are created by assigning a value with `=`, e.g., `my_name = "Amina"`.
- **print() Function**: This displays text or variable values to the screen. You can combine multiple items in a `print()` statement by separating them with commas, which automatically adds spaces between them.
- **Comments**: These are notes starting with `#` that Python ignores, used to explain what the code does. They help make the code easier to understand.

### Step-by-Step Breakdown of the Solution
1. **Create the file**: The program is saved as `greeting.py` in a text editor (e.g., Notepad or VS Code).
2. **Define variables**:
   - Create `my_name` to store a name as a string (e.g., `"Amina"`).
   - Create `fav_number` to store a number (e.g., `7`).
3. **Use print()**: Combine the variables into a sentence using `print()`. The commas in `print()` add spaces, so `print("Hello, my name is", my_name)` will display "Hello, my name is Amina" if `my_name = "Amina"`.
4. **Add comments**: Place a `#` comment above each line to explain its purpose, making the code clear for beginners.
5. **Run the program**: Save the file, open a command line, navigate to the file’s folder, and run `python greeting.py` to see the output.

### Why This Works
- The variables act like labeled boxes, holding your name and number for easy reuse.
- The `print()` function combines text and variables into a readable sentence.
- Comments ensure anyone reading the code (including you later!) understands what each line does.
- This simple program reinforces how to store and display data, a foundational skill for programming.

### Solution Code
Below is the complete code for `greeting.py`. I’ve used example values (`"Amina"` and `7`), but you can replace them with your own name and favorite number.

```python
# Define a variable to store the user's name
my_name = "Amina"

# Define a variable to store the user's favorite number
fav_number = 7

# Print a greeting that combines the name and favorite number
print("Hello, my name is", my_name, "and my favorite number is", fav_number, ".")
```

### Running the Code
- Save the code in a file named `greeting.py`.
- Open a command line (Command Prompt on Windows, Terminal on Mac/Linux).
- Navigate to the folder containing `greeting.py` using `cd` (e.g., `cd Desktop` if the file is on your Desktop).
- Run the program by typing `python greeting.py`.
- The output will be:
  ```
  Hello, my name is Amina and my favorite number is 7.
  ```

### Common Mistakes to Avoid
- **Forgetting quotes**: Strings like `"Amina"` need quotes; numbers like `7` do not.
- **Indentation errors**: All lines in this program should be aligned with no extra spaces at the start, as there’s no block (like an `if` statement) requiring indentation.
- **Spelling variables wrong**: If you write `my_name` as `My_name` in the `print()` statement, Python will give an error because variable names are case-sensitive.
- **Missing commas in print()**: Without commas between items in `print()`, Python will give a syntax error.

This solution is simple and practical, showing how variables and `print()` can create personalized output. It builds confidence by letting you see immediate results from your code.