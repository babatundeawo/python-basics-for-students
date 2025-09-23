# Instructional Guide for Python Variables

## Section 1 – Explanations

This lesson introduces **Python variables**, which are containers used to store data values. Below, I’ll explain the key concepts from the lesson, using the provided examples where applicable and keeping explanations beginner-friendly.

### Creating Variables
In Python, variables are created when you assign a value to them using the `=` operator. There’s no need to declare a variable type beforehand. For example:
```python
x = 5
y = "John"
print(x)  # Outputs: 5
print(y)  # Outputs: John
```
Here, `x` stores the integer `5`, and `y` stores the string `"John"`. Variables can hold different types of data, and their type can change after assignment. For example:
```python
x = 4       # x is an integer
x = "Sally" # x is now a string
print(x)    # Outputs: Sally
```

### Casting
You can specify a variable’s data type using **casting**. This involves converting a value to a specific type using functions like `str()`, `int()`, or `float()`. For example:
```python
x = str(3)    # x is '3' (string)
y = int(3)    # y is 3 (integer)
z = float(3)  # z is 3.0 (float)
```

### Getting the Type
To check a variable’s data type, use the `type()` function. For example:
```python
x = 5
y = "John"
print(type(x))  # Outputs: <class 'int'>
print(type(y))  # Outputs: <class 'str'>
```

### Single or Double Quotes
String variables can be declared using either single (`'`) or double (`"`) quotes—they work the same way. For example:
```python
x = "John"
x = 'John'  # Same as above
```

### Case Sensitivity
Variable names are **case-sensitive**, meaning `age`, `Age`, and `AGE` are treated as different variables. For example:
```python
a = 4
A = "Sally"
# 'a' and 'A' are distinct variables
```

### Variable Naming Rules
Variable names must follow these rules:
- Start with a letter or underscore (`_`).
- Contain only letters, numbers, and underscores (`A-z`, `0-9`, `_`).
- Cannot be Python keywords (e.g., `if`, `for`).
- Case-sensitive.

**Legal names**:
```python
myvar = "John"
my_var = "John"
_my_var = "John"
myVar = "John"
MYVAR = "John"
myvar2 = "John"
```

**Illegal names**:
```python
2myvar = "John"  # Starts with a number
my-var = "John"  # Contains a hyphen
my var = "John"  # Contains a space
```

### Multi-Word Variable Names
For readability, multi-word variable names can use:
- **Camel Case**: `myVariableName`
- **Pascal Case**: `MyVariableName`
- **Snake Case**: `my_variable_name`
Example:
```python
myVariableName = "John"  # Camel Case
MyVariableName = "John"  # Pascal Case
my_variable_name = "John"  # Snake Case
```

### Assigning Multiple Values
Python allows assigning values to multiple variables in one line:
```python
x, y, z = "Orange", "Banana", "Cherry"
print(x)  # Outputs: Orange
print(y)  # Outputs: Banana
print(z)  # Outputs: Cherry
```
You can also assign the same value to multiple variables:
```python
x = y = z = "Orange"
print(x)  # Outputs: Orange
print(y)  # Outputs: Orange
print(z)  # Outputs: Orange
```

### Unpacking a Collection
You can extract values from a list or tuple into variables (called **unpacking**):
```python
fruits = ["apple", "banana", "cherry"]
x, y, z = fruits
print(x)  # Outputs: apple
print(y)  # Outputs: banana
print(z)  # Outputs: cherry
```

### Outputting Variables
The `print()` function outputs variables. Multiple variables can be printed using commas or the `+` operator:
```python
x = "Python"
y = "is"
z = "awesome"
print(x, y, z)  # Outputs: Python is awesome
print(x + y + z)  # Outputs: Pythonisawesome
```
Note: When using `+` with strings, ensure spaces are included in the strings if needed. For numbers, `+` performs addition:
```python
x = 5
y = 10
print(x + y)  # Outputs: 15
```
Using `+` with a string and a number causes an error, so use commas instead:
```python
x = 5
y = "John"
print(x, y)  # Outputs: 5 John
```

### Global Variables
**Global variables** are created outside functions and can be used anywhere. For example:
```python
x = "awesome"

def myfunc():
    print("Python is " + x)

myfunc()  # Outputs: Python is awesome
```
If a variable with the same name is created inside a function, it’s **local** and doesn’t affect the global variable:
```python
x = "awesome"

def myfunc():
    x = "fantastic"
    print("Python is " + x)

myfunc()       # Outputs: Python is fantastic
print("Python is " + x)  # Outputs: Python is awesome
```

### The `global` Keyword
To create or modify a global variable inside a function, use the `global` keyword:
```python
def myfunc():
    global x
    x = "fantastic"

myfunc()
print("Python is " + x)  # Outputs: Python is fantastic
```
To change a global variable’s value inside a function:
```python
x = "awesome"

def myfunc():
    global x
    x = "fantastic"

myfunc()
print("Python is " + x)  # Outputs: Python is fantastic
```

## Section 2 – Class Exercise

This lesson supports a beginner-friendly exercise to reinforce variable creation, assignment, and output.

### Exercise: Create and Manipulate Variables
**Objective**: Practice creating variables, assigning different data types, and outputting them.

**Steps**:
1. Create a variable named `name` and assign it your name as a string (use either single or double quotes).
2. Create a variable named `age` and assign it your age as an integer.
3. Create a variable named `height` and assign it your height (in meters or feet) as a float.
4. Print all three variables in one line using commas in the `print()` function.
5. Change the value of `name` to a different name and print it again.
6. Use the `type()` function to print the data type of each variable.

**Guidance**:
- Use the `=` operator to assign values.
- For the float, include a decimal point (e.g., `1.75` for 1.75 meters).
- When printing multiple variables, separate them with commas in the `print()` function.
- To change `name`, assign a new string value to it.
- Use `type()` like this: `print(type(name))`.

## Section 3 – Weekly Project

This lesson supports a simple project to practice variable naming, multiple assignments, and output.

### Project: Personal Profile Card
**Objective**: Create a program that stores and displays information about a person using variables.

**Guidelines**:
1. Create variables for the following pieces of information:
   - `first_name` (string): The person’s first name.
   - `last_name` (string): The person’s last name.
   - `age` (integer): The person’s age.
   - `hobby` (string): The person’s favorite hobby.
   - Use **snake_case** for variable names.
2. Assign appropriate values to each variable.
3. Print a sentence using these variables, like: `"Hello, my name is [first_name] [last_name], I am [age] years old, and I enjoy [hobby]."`. Use commas in the `print()` function to combine the variables and text.
4. Create a list called `favorites` containing three favorite things (e.g., foods, activities, or colors).
5. Unpack the `favorites` list into three variables (e.g., `fav1`, `fav2`, `fav3`).
6. Print the unpacked variables in a sentence, like: `"My favorite things are [fav1], [fav2], and [fav3]."`.

**Tips**:
- Use clear, descriptive variable names following the naming rules.
- When printing, ensure strings have spaces where needed to make the output readable.
- For unpacking, ensure the number of variables matches the number of items in the `favorites` list.
- Experiment with different values to make the profile your own!