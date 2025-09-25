# Python Variables for Complete Beginners

## Section 1 – Explanations

Variables in Python are like labeled boxes where you can store information, such as numbers, text, or other data. You create a variable by giving it a name and assigning a value to it using the `=` sign. Python doesn’t require you to declare a variable’s type, and you can even change the type of data stored in a variable later.

Let’s break down the key concepts from the lesson:

1. **Creating Variables**:
   - A variable is created when you assign a value to it. For example:
     ```python
     x = 5       # Stores the number 5 in variable x
     y = "John"  # Stores the text "John" in variable y
     print(x)    # Outputs: 5
     print(y)    # Outputs: John
     ```
   - Here, `x` holds a number (integer), and `y` holds text (string). You don’t need to specify the type—Python figures it out automatically.

2. **Changing Variable Types**:
   - Variables can change types after being set. For example:
     ```python
     x = 4           # x is an integer
     x = "Sally"     # x is now a string
     print(x)        # Outputs: Sally
     ```
   - This flexibility makes Python easy to use, as you can reassign variables without restrictions.

3. **Casting**:
   - You can force a variable to be a specific type using casting. For example:
     ```python
     x = str(3)    # x is '3' (string)
     y = int(3)    # y is 3 (integer)
     z = float(3)  # z is 3.0 (floating-point number)
     print(x, y, z)  # Outputs: 3 3 3.0
     ```
   - Casting is useful when you need a specific data type for calculations or display.

4. **Checking Types**:
   - Use the `type()` function to check a variable’s data type:
     ```python
     x = 5
     y = "John"
     print(type(x))  # Outputs: <class 'int'>
     print(type(y))  # Outputs: <class 'str'>
     ```
   - This helps you understand what kind of data you’re working with.

5. **Variable Naming Rules**:
   - Variable names must start with a letter or underscore (`_`), not a number.
   - Names can include letters, numbers, and underscores (e.g., `my_var2`).
   - Names are case-sensitive, so `age` and `Age` are different variables.
   - Examples of valid names:
     ```python
     myvar = "John"
     my_var = "John"
     myVar2 = "John"
     ```
   - Invalid names (will cause errors):
     ```python
     2myvar = "John"  # Starts with a number
     my-var = "John"  # Contains a hyphen
     my var = "John"  # Contains a space
     ```

6. **Naming Conventions**:
   - For multi-word variable names, use:
     - **Camel Case**: `myVariableName`
     - **Pascal Case**: `MyVariableName`
     - **Snake Case**: `my_variable_name`
   - Snake case is common in Python for readability:
     ```python
     my_variable_name = "John"
     print(my_variable_name)  # Outputs: John
     ```

7. **Assigning Multiple Values**:
   - Assign values to multiple variables in one line:
     ```python
     x, y, z = "Orange", "Banana", "Cherry"
     print(x, y, z)  # Outputs: Orange Banana Cherry
     ```
   - Assign the same value to multiple variables:
     ```python
     x = y = z = "Orange"
     print(x, y, z)  # Outputs: Orange Orange Orange
     ```
   - Unpack a list into variables:
     ```python
     fruits = ["apple", "banana", "cherry"]
     x, y, z = fruits
     print(x, y, z)  # Outputs: apple banana cherry
     ```

8. **Outputting Variables**:
   - Use the `print()` function to display variables:
     ```python
     x = "Python is awesome"
     print(x)  # Outputs: Python is awesome
     ```
   - Print multiple variables with commas (works with different types):
     ```python
     x = 5
     y = "John"
     print(x, y)  # Outputs: 5 John
     ```
   - Using `+` to combine strings requires careful handling:
     ```python
     x = "Python "
     y = "is "
     z = "awesome"
     print(x + y + z)  # Outputs: Python is awesome
     ```
   - Note: `+` doesn’t work directly with numbers and strings (e.g., `print(5 + "John")` causes an error).

9. **Global Variables**:
   - Variables created outside a function are global and can be used anywhere:
     ```python
     x = "awesome"

     def myfunc():
         print("Python is " + x)

     myfunc()  # Outputs: Python is awesome
     ```
   - Variables inside a function are local by default:
     ```python
     x = "awesome"

     def myfunc():
         x = "fantastic"  # Local variable
         print("Python is " + x)

     myfunc()       # Outputs: Python is fantastic
     print("Python is " + x)  # Outputs: Python is awesome
     ```
   - Use the `global` keyword to modify a global variable inside a function:
     ```python
     x = "awesome"

     def myfunc():
         global x
         x = "fantastic"  # Changes the global variable
         print("Python is " + x)

     myfunc()       # Outputs: Python is fantastic
     print("Python is " + x)  # Outputs: Python is fantastic
     ```

These concepts form the foundation of working with variables in Python, allowing you to store and manipulate data effectively.

## Section 2 – Class Exercise

**Exercise: Create a Simple Profile Card**

In this exercise, you’ll create a program that stores and displays a person’s profile information using variables. This reinforces variable creation, naming, and outputting.

**Steps**:
1. Create three variables: `name` (string), `age` (integer), and `hobby` (string).
2. Assign your own values to these variables (e.g., your name, age, and favorite hobby).
3. Use the `print()` function to display a sentence like: "My name is [name], I am [age] years old, and my favorite hobby is [hobby]."
4. Try using both commas and the `+` operator in separate `print()` statements to combine the variables.
5. Bonus: Check the type of each variable using `type()` and print the results.

**Guidance**:
- Use snake_case for variable names (e.g., `my_name`).
- If using `+`, ensure all variables are strings (cast numbers if needed, e.g., `str(age)`).
- Test your program to ensure it outputs the sentence correctly.

This exercise helps you practice creating variables, assigning values, and outputting them in a practical way.

## Section 3 – Weekly Project

**Weekly Project: Personal Budget Tracker**

In this project, you’ll create a simple program to track weekly expenses using variables. This combines variable creation, casting, and outputting, while encouraging creativity.

**Project Brief**:
Create a program that tracks a user’s weekly budget for three categories: food, transport, and entertainment. The program should:
1. Store the amount spent in each category as variables (use integers or floats).
2. Calculate the total spent by adding the variables.
3. Display a summary of the expenses, including the individual amounts and the total.
4. Use appropriate variable names (e.g., `food_expense`, `transport_expense`).
5. Output the summary in a clear sentence, like: "This week, you spent $X on food, $Y on transport, $Z on entertainment, totaling $T."

**Milestones**:
1. Create three variables for `food_expense`, `transport_expense`, and `entertainment_expense` with sample values (e.g., `50.25`, `30`, `20.75`).
2. Create a variable `total_expense` by adding the three expense variables.
3. Use `print()` to display the summary, experimenting with commas or `+` for string concatenation.
4. Ensure numbers are displayed correctly (cast to strings if using `+`).
5. Test your program with different values to confirm the total is correct.

**Extension Ideas**:
- Add a variable for the weekly budget and print whether the total spending is under or over the budget.
- Try storing the expense categories and amounts in a list and unpack them into variables.
- Experiment with formatting the output to make it look like a neat receipt.

This project reinforces variables, basic arithmetic, and output, while introducing the idea of organizing data (hinting at lists, a future topic). It’s practical and encourages creative additions like budget comparisons.