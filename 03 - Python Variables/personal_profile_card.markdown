# Answers to Python Variables Weekly Project

Below are the answers to the **Personal Profile Card** project, designed for complete beginners to practice variable naming, multiple assignments, and output. The answers follow the guidelines provided in the project, ensuring clarity and simplicity while leaving room for student creativity.

### Project: Personal Profile Card
**Objective**: Create a program that stores and displays information about a person using variables.

**Guidelines and Answers**:

1. **Create variables for the following pieces of information:**
   - `first_name` (string): The person’s first name.
   - `last_name` (string): The person’s last name.
   - `age` (integer): The person’s age.
   - `hobby` (string): The person’s favorite hobby.
   - Use **snake_case** for variable names.
   ```python
   first_name = "Emma"
   last_name = "Smith"
   age = 25
   hobby = "painting"
   ```

2. **Assign appropriate values to each variable.**
   - Values are assigned in the step above. These are example values; students should use their own information.

3. **Print a sentence using these variables, like: `"Hello, my name is [first_name] [last_name], I am [age] years old, and I enjoy [hobby]."`. Use commas in the `print()` function to combine the variables and text.**
   ```python
   print("Hello, my name is", first_name, last_name, ", I am", age, "years old, and I enjoy", hobby, ".")
   # Output: Hello, my name is Emma Smith , I am 25 years old, and I enjoy painting .
   ```

4. **Create a list called `favorites` containing three favorite things (e.g., foods, activities, or colors).**
   ```python
   favorites = ["pizza", "hiking", "blue"]
   ```

5. **Unpack the `favorites` list into three variables (e.g., `fav1`, `fav2`, `fav3`).**
   ```python
   fav1, fav2, fav3 = favorites
   ```

6. **Print the unpacked variables in a sentence, like: `"My favorite things are [fav1], [fav2], and [fav3]."`.**
   ```python
   print("My favorite things are", fav1, ",", fav2, ", and", fav3, ".")
   # Output: My favorite things are pizza , hiking , and blue .
   ```

**Complete Code**:
```python
first_name = "Emma"
last_name = "Smith"
age = 25
hobby = "painting"
print("Hello, my name is", first_name, last_name, ", I am", age, "years old, and I enjoy", hobby, ".")
favorites = ["pizza", "hiking", "blue"]
fav1, fav2, fav3 = favorites
print("My favorite things are", fav1, ",", fav2, ", and", fav3, ".")
```

**Notes**:
- The values for `first_name`, `last_name`, `age`, `hobby`, and `favorites` are examples. Students should personalize them.
- Using commas in the `print()` function automatically adds spaces between values, making the output readable.
- The `favorites` list is unpacked into three variables, reinforcing the concept of unpacking collections.
- Students can experiment with different values or additional text to make the output more creative, as long as they follow the variable naming rules and structure.