# Instructional Guide for Python Variables

---

## Section 1 – Explanations

In Python, **variables** are used to store data values, acting like labeled containers. You don’t need a special command to declare a variable; it’s created as soon as you assign a value to it using the `=` operator. For example:

```python
x = 5       # x stores the integer 5
y = "John"  # y stores the string "John"
print(x)    # Outputs: 5
print(y)    # Outputs: John
```

Variables are flexible and don’t require a specific data type. You can even change a variable’s type after it’s set:

```python
x = 4         # x is an integer
x = "Sally"   # x is now a string
print(x)      # Outputs: Sally
```

**Casting** lets you specify a variable’s data type explicitly:

```python
x = str(3)    # x is '3' (string)
y = int(3)    # y is 3 (integer)
z = float(3)  # z is 3.0 (float)
```

To check a variable’s type, use the `type()` function:

```python
x = 5
y = "John"
print(type(x))  # Outputs: <class 'int'>
print(type(y))  # Outputs: <class 'str'>
```

**String variables** can use single or double quotes interchangeably:

```python
x = "John"  # Double quotes
x = 'John'  # Single quotes, same result
```

Variable names are **case-sensitive** (`a` and `A` are different variables) and must follow these rules:
- Start with a letter or underscore (`_`).
- Contain only letters, numbers, and underscores.
- Cannot be Python keywords (e.g., `if`, `for`).
- Examples of legal names: `myvar`, `my_var`, `_myvar`, `myVar2`.
- Illegal names: `2myvar`, `my-var`, `my var`.

For multi-word variable names, use:
- **Camel Case**: `myVariableName`
- **Pascal Case**: `MyVariableName`
- **Snake Case**: `my_variable_name`

You can assign multiple values to multiple variables in one line:

```python
x, y, z = "Orange", "Banana", "Cherry"
print(x, y, z)  # Outputs: Orange Banana Cherry
```

Or assign the same value to multiple variables:

```python
x = y = z = "Orange"
print(x, y, z)  # Outputs: Orange Orange Orange
```

**Unpacking** lets you extract values from a list or tuple into variables:

```python
fruits = ["apple", "banana", "cherry"]
x, y, z = fruits
print(x, y, z)  # Outputs: apple banana cherry
```

To **output variables**, use the `print()` function. Separate multiple variables with commas to avoid errors when mixing types:

```python
x = 5
y = "John"
print(x, y)  # Outputs: 5 John
```

Using `+` concatenates strings but works as a mathematical operator for numbers. Mixing types with `+` causes errors:

```python
x = "Python "
y = "is "
z = "awesome"
print(x + y + z)  # Outputs: Python is awesome
x = 5
y = 10
print(x + y)      # Outputs: 15
```

**Global variables** are defined outside functions and can be used anywhere:

```python
x = "awesome"

def myfunc():
    print("Python is " + x)

myfunc()  # Outputs: Python is awesome
```

Inside a function, a variable with the same name as a global variable is **local** by default and doesn’t affect the global one:

```python
x = "awesome"

def myfunc():
    x = "fantastic"
    print("Python is " + x)

myfunc()        # Outputs: Python is fantastic
print("Python is " + x)  # Outputs: Python is awesome
```

The `global` keyword lets you create or modify a global variable inside a function:

```python
def myfunc():
    global x
    x = "fantastic"

myfunc()
print("Python is " + x)  # Outputs: Python is fantastic
```

---

## Section 2 – Class Exercise

**Exercise: Track a Small Store’s Inventory**

You’re helping a small store track items and their prices. Use variables to store and display information about three products.

**Steps:**
1. Create three variables for product names (e.g., `item1`, `item2`, `item3`) and assign them string values (e.g., "Apple", "Banana", "Orange").
2. Create three variables for their prices (e.g., `price1`, `price2`, `price3`) and assign them numeric values (use integers or floats, e.g., 0.5, 0.75, 1.0).
3. Print each product and its price in a readable format using commas in the `print()` function (e.g., `Item: Apple, Price: 0.5`).
4. Calculate and print the total price of all three items using the `+` operator.

**Guidance:**
- Use descriptive variable names (e.g., `item1` or `apple_price`).
- Ensure the number of variables matches the values when assigning.
- Use commas in `print()` to combine strings and numbers safely.
- Test your code to check for errors, like mismatched types or variable names.

---

## Section 3 – Weekly Project

**Project: Personal Budget Planner**

You’re building a simple budget planner to track monthly expenses. This project uses variables, multiple value assignments, and output formatting to help a user organize their spending.

**Project Brief:**
Create a program that:
1. Stores three expense categories (e.g., food, transport, entertainment) and their monthly costs.
2. Calculates the total and average monthly spending.
3. Outputs the expenses and summary in a clear format.

**Step-by-Step Guidelines:**
1. Use multiple variable assignment to create three variables for expense categories (e.g., `food, transport, entertainment = 200, 150, 100`).
2. Calculate the total spending by adding the three expense values using the `+` operator.
3. Calculate the average spending by dividing the total by 3 (use a variable to store this).
4. Print each category and its cost using `print()` with commas for readability (e.g., `Food: 200`).
5. Print the total and average spending in a clear format.
6. Experiment with formatting: try using snake_case or camelCase for variable names to make them readable.
7. (Curiosity nudge) Think about how you might store these expenses in a list for easier management in the future. You don’t need to implement this yet, but consider what benefits a list might offer.

**Tips:**
- Use clear variable names to make your code easy to understand.
- Test your program with different expense values to ensure calculations are correct.
- Use `print()` with commas to combine strings and numbers, avoiding errors with the `+` operator.
- Be creative with how you display the output (e.g., add a header like "Monthly Budget Summary").

This project builds confidence with variables and introduces the idea of collections (like lists), which you’ll explore in future lessons.