# Solution to Python Numbers Weekly Project

The weekly project asked you to create a program that allows users to input a whole number and a decimal number, perform type conversions, and generate a random number. Below is a solution that follows the project guidelines. This is provided to help you understand how to approach the task, but you should try writing the code yourself first to reinforce your learning.

## Project Solution

The project required you to:
1. Ask the user to input a whole number (integer) and a decimal number (float) using `input()`.
2. Store the inputs and convert them to the appropriate types (`int` and `float`).
3. Perform type conversions: integer to float, float to integer, and integer to complex.
4. Print the original numbers, their converted values, and their types using `type()`.
5. Generate a random integer between 1 and 50 using the `random` module.
6. Ensure clear prompts and proper handling of inputs.

Here is a Python program that accomplishes these tasks:

```python
import random

# Step 1: Get user input for a whole number and a decimal number
whole_number = input("Enter a whole number: ")
decimal_number = input("Enter a decimal number: ")

# Step 2: Convert inputs to appropriate types
try:
    my_int = int(whole_number)
    my_float = float(decimal_number)
except ValueError:
    print("Error: Please enter valid numbers (whole number and decimal number).")
    exit()

# Step 3: Perform type conversions
int_to_float = float(my_int)    # Convert integer to float
float_to_int = int(my_float)    # Convert float to integer
int_to_complex = complex(my_int)  # Convert integer to complex

# Step 4: Print original numbers, converted values, and their types
print("\nOriginal Numbers:")
print("Whole number:", my_int, "Type:", type(my_int))
print("Decimal number:", my_float, "Type:", type(my_float))

print("\nConverted Values:")
print("Integer to float:", int_to_float, "Type:", type(int_to_float))
print("Float to integer:", float_to_int, "Type:", type(float_to_int))
print("Integer to complex:", int_to_complex, "Type:", type(int_to_complex))

# Step 5: Generate and print a random integer between 1 and 50
random_number = random.randrange(1, 51)  # 51 is exclusive, so range is 1 to 50
print("\nRandom number between 1 and 50:", random_number)
```

### Expected Output
If the user inputs `10` for the whole number and `5.75` for the decimal number, the output might look like this (the random number will vary):
```
Enter a whole number: 10
Enter a decimal number: 5.75

Original Numbers:
Whole number: 10 Type: <class 'int'>
Decimal number: 5.75 Type: <class 'float'>

Converted Values:
Integer to float: 10.0 Type: <class 'float'>
Float to integer: 5 Type: <class 'int'>
Integer to complex: (10+0j) Type: <class 'complex'>

Random number between 1 and 50: 42
```

If the user enters invalid input (e.g., letters instead of numbers), the output will be:
```
Enter a whole number: abc
Enter a decimal number: 5.75
Error: Please enter valid numbers (whole number and decimal number).
```

### Explanation of the Solution
- **Step 1**: The `input()` function prompts the user for a whole number and a decimal number, storing the inputs as strings.
- **Step 2**: The inputs are converted to `int` and `float` using `int()` and `float()`. A `try-except` block handles invalid inputs (e.g., non-numeric values) by printing an error message and exiting the program.
- **Step 3**: The required type conversions are performed: integer to float, float to integer (truncating the decimal part), and integer to complex.
- **Step 4**: The program prints the original numbers, their types, the converted values, and their types, using clear labels for readability.
- **Step 5**: The `random.randrange(1, 51)` function generates a random integer from 1 to 50 (51 is exclusive). The `random` module is imported at the start.
- **Error Handling**: The `try-except` block ensures the program doesn’t crash if the user enters invalid input, making it more user-friendly.

### Tips for Beginners
- **Input Handling**: The `input()` function returns a string, so you must convert it to the correct type (`int` or `float`). Always include error handling to manage invalid inputs.
- **Type Conversion**: Remember that converting a float to an integer truncates the decimal part (e.g., `5.75` becomes `5`).
- **Random Numbers**: The `random.randrange(1, 51)` function generates numbers from 1 to 50. Test the program multiple times to see different random outputs.
- **Formatting Output**: Use `\n` in print statements to add blank lines for better readability.
- **Testing**: Try inputs like negative numbers, zero, or large numbers to ensure the program works correctly. Also test with invalid inputs to verify error handling.

This solution provides a clear, beginner-friendly program that meets the project requirements while reinforcing numeric types, type conversion, user input, and random number generation in Python.