# Python Numbers Lesson

## Section 1 – Explanations

In Python, there are three main numeric types: **int**, **float**, and **complex**. These types allow you to work with different kinds of numbers in your programs.

1. **Integers (int)**: These are whole numbers, positive or negative, without any decimal points. They have unlimited length, meaning Python can handle very large integers without issue.
   - Example:
     ```python
     x = 1
     y = 35656222554887711
     z = -3255522
     print(type(x))  # Output: <class 'int'>
     print(type(y))  # Output: <class 'int'>
     print(type(z))  # Output: <class 'int'>
     ```

2. **Floats (float)**: These are numbers that include one or more decimal points, representing real numbers. They can be positive or negative. Floats can also be written in scientific notation using "e" to indicate powers of 10.
   - Example:
     ```python
     x = 1.10
     y = 1.0
     z = -35.59
     print(type(x))  # Output: <class 'float'>
     print(type(y))  # Output: <class 'float'>
     print(type(z))  # Output: <class 'float'>
     ```
   - Scientific notation example:
     ```python
     x = 35e3    # 35 * 10^3 = 35000.0
     y = 12E4    # 12 * 10^4 = 120000.0
     z = -87.7e100
     print(type(x))  # Output: <class 'float'>
     print(type(y))  # Output: <class 'float'>
     print(type(z))  # Output: <class 'float'>
     ```

3. **Complex Numbers (complex)**: These are numbers with a real part and an imaginary part, where the imaginary part is denoted by "j". They are used in advanced mathematical computations.
   - Example:
     ```python
     x = 3+5j
     y = 5j
     z = -5j
     print(type(x))  # Output: <class 'complex'>
     print(type(y))  # Output: <class 'complex'>
     print(type(z))  # Output: <class 'complex'>
     ```

4. **Type Conversion**: You can convert between numeric types using the `int()`, `float()`, and `complex()` functions, but complex numbers cannot be converted to other types.
   - Example:
     ```python
     x = 1    # int
     y = 2.8  # float
     z = 1j   # complex

     a = float(x)    # Convert int to float: 1.0
     b = int(y)      # Convert float to int: 2
     c = complex(x)  # Convert int to complex: (1+0j)

     print(a)        # Output: 1.0
     print(b)        # Output: 2
     print(c)        # Output: (1+0j)
     print(type(a))  # Output: <class 'float'>
     print(type(b))  # Output: <class 'int'>
     print(type(c))  # Output: <class 'complex'>
     ```

5. **Random Numbers**: Python’s `random` module allows you to generate random numbers. The `random.randrange(start, stop)` function generates a random integer between `start` (inclusive) and `stop` (exclusive).
   - Example:
     ```python
     import random
     print(random.randrange(1, 10))  # Outputs a random integer from 1 to 9
     ```

You can verify the type of any variable using the `type()` function, as shown in the examples above.

## Section 2 – Class Exercise

This exercise will help you practice working with Python’s numeric types and type conversion.

**Exercise: Exploring Numeric Types and Conversions**

1. Create three variables:
   - An integer with the value `10`.
   - A float with the value `5.75`.
   - A complex number with the value `2+3j`.
2. Use the `type()` function to print the type of each variable.
3. Perform the following type conversions:
   - Convert the integer to a float.
   - Convert the float to an integer.
   - Convert the integer to a complex number.
4. Print the results of each conversion and their types.
5. Use the `random` module to generate and print a random integer between 1 and 100.

**Guidelines**:
- Write the code in a Python editor or environment.
- Make sure to import the `random` module for the last step.
- Check the output to ensure the conversions are correct and the types match what you expect.

## Section 3 – Weekly Project

**Project: Simple Number Converter and Randomizer**

**Objective**: Create a small program that allows users to input a number, convert it between types, and generate a random number.

**Guidelines**:
1. Ask the user to input a whole number (integer) and a decimal number (float) using the `input()` function.
2. Store these inputs in variables and convert them to the appropriate types (use `int()` for the whole number and `float()` for the decimal number).
3. Perform the following conversions:
   - Convert the integer to a float.
   - Convert the float to an integer.
   - Convert the integer to a complex number.
4. Print the original numbers, their converted values, and their types using `type()`.
5. Use the `random` module to generate a random integer between 1 and 50 and print it.
6. Ensure the program handles the inputs correctly (e.g., use proper prompts to guide the user).

**Tips**:
- Use clear prompts like `"Enter a whole number: "` and `"Enter a decimal number: "` for user input.
- Test your program with different inputs to ensure it works as expected.
- Be creative with how you display the output to make it clear and readable.

This project reinforces the concepts of numeric types, type conversion, and using the random module while introducing basic user input.