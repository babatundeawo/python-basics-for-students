# Solution to Personal Profile Creator Exercise

## Explanation

The **Personal Profile Creator** exercise requires building a Python program that collects a user’s name (string), age (integer), and height (float), stores them in variables, and displays a summary message. Additionally, it uses the `type()` function to confirm the data types of the variables. This solution reinforces the concepts of data types, casting, and input/output, which are central to the lesson on Python data types.

### Step-by-Step Breakdown
1. **Collecting Input**:
   - We use the `input()` function to get user input for name, age, and height.
   - Since `input()` always returns a string, we need to cast the age to an integer (`int()`) and the height to a float (`float()`).

2. **Storing in Variables**:
   - The name is stored as a string (no casting needed).
   - The age is cast to an integer to ensure it’s a whole number.
   - The height is cast to a float to allow for decimal values (e.g., 1.75 meters).

3. **Displaying the Summary**:
   - We use a `print()` statement to combine the inputs into a single message.
   - The message format is: `"Hi, [name]! You are [age] years old and [height] meters tall."`

4. **Checking Data Types**:
   - We use `type()` to print the data type of each variable (e.g., `<class 'str'>`, `<class 'int'>`, `<class 'float'>`).
   - This confirms that the variables are stored with the correct data types.

### Why This Works
- The program uses **strings** for the name, **integers** for the age, and **floats** for the height, aligning with the lesson’s focus on data types.
- **Casting** ensures that inputs are converted to the appropriate type (e.g., `"25"` becomes `25` for age).
- The `type()` function helps beginners verify that their variables are correctly typed, building confidence in understanding data types.
- The exercise mimics a real-world scenario, like filling out a profile form, making it relatable and practical.

### Solution Code
Below is the complete Python code for the Personal Profile Creator, followed by sample output.

```python
# Get user input for name, age, and height
name = input("Enter your name: ")
age = int(input("Enter your age: "))
height = float(input("Enter your height in meters: "))

# Print the summary message
print("Hi,", name, "! You are", age, "years old and", height, "meters tall.")

# Print the data types of each variable
print("Data type of name:", type(name))
print("Data type of age:", type(age))
print("Data type of height:", type(height))
```

### Sample Output
If the user enters:
- Name: Amina
- Age: 15
- Height: 1.75

The output will be:
```
Enter your name: Amina
Enter your age: 15
Enter your height in meters: 1.75
Hi, Amina! You are 15 years old and 1.75 meters tall.
Data type of name: <class 'str'>
Data type of age: <class 'int'>
Data type of height: <class 'float'>
```

### Notes for Beginners
- **Error Handling**: This basic version assumes valid inputs (e.g., numbers for age and height). In a real program, you might want to add checks for invalid inputs (e.g., non-numeric values), which you’ll learn about later with conditionals and error handling.
- **Casting**: The `int()` and `float()` functions are used to convert string inputs to numbers. If you forget to cast, Python will treat the input as a string, which could cause errors in calculations (a future topic).
- **Practice Tip**: Try running the program with different inputs (e.g., a decimal age or a negative height) to see what happens. This will help you understand casting and data types better.

This solution is simple, practical, and directly applies the lesson’s concepts, helping you build confidence in working with Python’s data types.