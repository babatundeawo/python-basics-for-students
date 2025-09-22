# Solution to Python Numbers Class Exercise

The exercise asked you to practice working with Python’s numeric types and type conversion. Below is a solution that follows the steps outlined in the exercise. This is provided to help you understand how to approach the task, but you should try writing the code yourself first to reinforce your learning.

## Exercise Solution

The exercise required you to:
1. Create three variables: an integer (`10`), a float (`5.75`), and a complex number (`2+3j`).
2. Print the type of each variable using `type()`.
3. Perform type conversions: integer to float, float to integer, and integer to complex.
4. Print the results of each conversion and their types.
5. Generate a random integer between 1 and 100 using the `random` module.

Here is a Python program that accomplishes these tasks:

```python
import random

# Step 1: Create variables with different numeric types
my_int = 10
my_float = 5.75
my_complex = 2 + 3j

# Step 2: Print the type of each variable
print("Type of my_int:", type(my_int))
print("Type of my_float:", type(my_float))
print("Type of my_complex:", type(my_complex))

# Step 3: Perform type conversions
int_to_float = float(my_int)    # Convert integer to float
float_to_int = int(my_float)    # Convert float to integer
int_to_complex = complex(my_int)  # Convert integer to complex

# Step 4: Print the converted values and their types
print("Integer to float:", int_to_float)
print("Type of int_to_float:", type(int_to_float))
print("Float to integer:", float_to_int)
print("Type of float_to_int:", type(float_to_int))
print("Integer to complex:", int_to_complex)
print("Type of int_to_complex:", type(int_to_complex))

# Step 5: Generate and print a random integer between 1 and 100
random_number = random.randrange(1, 101)  # 101 is exclusive, so range is 1 to 100
print("Random number between 1 and 100:", random_number)
```

### Expected Output
When you run the program, the output will look something like this (the random number will vary):
```
Type of my_int: <class 'int'>
Type of my_float: <class 'float'>
Type of my_complex: <class 'complex'>
Integer to float: 10.0
Type of int_to_float: <class 'float'>
Float to integer: 5
Type of float_to_int: <class 'int'>
Integer to complex: (10+0j)
Type of int_to_complex: <class 'complex'>
Random number between 1 and 100: 42
```

### Explanation of the Solution
- **Step 1**: We created three variables with the specified values: `my_int = 10`, `my_float = 5.75`, and `my_complex = 2 + 3j`.
- **Step 2**: The `type()` function is used to print the type of each variable, confirming they are `<class 'int'>`, `<class 'float'>`, and `<class 'complex'>`.
- **Step 3**: We performed the required type conversions using `float()`, `int()`, and `complex()`. Note that converting a float to an integer truncates the decimal part (e.g., `5.75` becomes `5`).
- **Step 4**: The converted values and their types are printed to verify the conversions.
- **Step 5**: The `random.randrange(1, 101)` function generates a random integer from 1 to 100 (101 is exclusive). The `random` module is imported at the start to enable this functionality.

### Tips for Beginners
- Ensure you import the `random` module before using `random.randrange()`.
- When converting a float to an integer, remember that the decimal part is discarded, not rounded.
- Test the program multiple times to see different random numbers in the output.
- If you encounter errors, check your syntax, especially for the complex number (use `j` for the imaginary part) and the `random.randrange()` arguments.

This solution provides a clear and simple way to complete the exercise while reinforcing the concepts of numeric types, type conversion, and random number generation in Python.