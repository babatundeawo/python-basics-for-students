# Solution to Class Exercise: Create a Simple Profile Card

This document provides a solution to the "Simple Profile Card" exercise, which reinforces the use of variables, naming conventions, and outputting data in Python. Below is an explanation of the solution, followed by the complete code.

## Explanation

The exercise requires creating a Python program that:
1. Defines three variables: `name` (string), `age` (integer), and `hobby` (string).
2. Assigns personal values to these variables.
3. Outputs a sentence combining these variables using both commas and the `+` operator in separate `print()` statements.
4. Optionally checks the type of each variable using the `type()` function.

### Key Concepts Applied
- **Variable Creation**: We create variables by assigning values using the `=` operator.
- **Variable Naming**: We use snake_case (e.g., `my_name`) for readability, as it’s a common Python convention.
- **Output with `print()`**:
  - Using commas in `print()` allows combining different data types (e.g., strings and integers) easily, with automatic spacing.
  - Using the `+` operator requires converting numbers to strings (casting with `str()`) to avoid errors.
- **Type Checking**: The `type()` function shows the data type of each variable, helping beginners understand Python’s dynamic typing.

### Step-by-Step Solution
1. **Define Variables**:
   - Create `my_name` as a string (e.g., "Amina").
   - Create `my_age` as an integer (e.g., 15).
   - Create `my_hobby` as a string (e.g., "reading").
2. **Output Using Commas**:
   - Use `print()` with commas to combine the variables into a sentence. Commas automatically add spaces and handle different data types.
3. **Output Using `+`**:
   - Use `print()` with the `+` operator, casting `my_age` to a string using `str(my_age)` to concatenate it with other strings.
4. **Check Types**:
   - Use `print(type(variable))` for each variable to display their types (e.g., `<class 'str'>` for strings, `<class 'int'>` for integers).

### Why This Works
- The comma-based `print()` is beginner-friendly because it handles different types without needing casting.
- The `+` operator demonstrates the need for type consistency (strings only) and introduces casting.
- Checking types reinforces understanding of Python’s dynamic typing system.
- Using snake_case ensures the code follows Python’s naming conventions, making it readable and professional.

## Solution Code

Below is the complete Python code for the exercise, implementing all requirements.

```python
# Define variables with personal values
my_name = "Amina"
my_age = 15
my_hobby = "reading"

# Output using commas (handles different types and adds spaces)
print("My name is", my_name, ", I am", my_age, "years old, and my favorite hobby is", my_hobby, ".")

# Output using + operator (requires casting numbers to strings)
print("My name is " + my_name + ", I am " + str(my_age) + " years old, and my favorite hobby is " + my_hobby + ".")

# Check the type of each variable
print("Type of my_name:", type(my_name))
print("Type of my_age:", type(my_age))
print("Type of my_hobby:", type(my_hobby))
```

### Expected Output
```
My name is Amina , I am 15 years old, and my favorite hobby is reading .
My name is Amina, I am 15 years old, and my favorite hobby is reading.
Type of my_name: <class 'str'>
Type of my_age: <class 'int'>
Type of my_hobby: <class 'str'>
```

### Notes for Beginners
- The comma-based `print()` is simpler because it doesn’t require casting and adds spaces automatically.
- The `+` operator needs `str(my_age)` because you can’t concatenate an integer with a string directly.
- The `type()` function helps you confirm that `my_name` and `my_hobby` are strings (`str`), while `my_age` is an integer (`int`).
- Try changing the values of `my_name`, `my_age`, and `my_hobby` to your own information to personalize the output!

This solution builds confidence by showing how variables can be used to store and display meaningful information in a real-world context, like a profile card.