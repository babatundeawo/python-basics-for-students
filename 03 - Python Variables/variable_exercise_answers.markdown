# Answers to Python Variables Class Exercise

Below are the answers to the **Create and Manipulate Variables** exercise, designed for complete beginners to practice creating variables, assigning different data types, and outputting them. The answers follow the steps provided in the exercise, ensuring clarity and simplicity.

### Exercise: Create and Manipulate Variables
**Objective**: Practice creating variables, assigning different data types, and outputting them.

**Steps and Answers**:

1. **Create a variable named `name` and assign it your name as a string (use either single or double quotes).**
   ```python
   name = "Alice"
   ```

2. **Create a variable named `age` and assign it your age as an integer.**
   ```python
   age = 20
   ```

3. **Create a variable named `height` and assign it your height (in meters or feet) as a float.**
   ```python
   height = 1.65
   ```

4. **Print all three variables in one line using commas in the `print()` function.**
   ```python
   print(name, age, height)
   # Output: Alice 20 1.65
   ```

5. **Change the value of `name` to a different name and print it again.**
   ```python
   name = "Bob"
   print(name)
   # Output: Bob
   ```

6. **Use the `type()` function to print the data type of each variable.**
   ```python
   print(type(name))   # Output: <class 'str'>
   print(type(age))    # Output: <class 'int'>
   print(type(height)) # Output: <class 'float'>
   ```

**Complete Code**:
```python
name = "Alice"
age = 20
height = 1.65
print(name, age, height)
name = "Bob"
print(name)
print(type(name))
print(type(age))
print(type(height))
```

**Notes**:
- The values for `name`, `age`, and `height` are examples. Students should use their own information.
- The `print()` function with commas automatically adds spaces between values in the output.
- The `type()` function shows the data type of each variable, helping reinforce the concept of different data types.