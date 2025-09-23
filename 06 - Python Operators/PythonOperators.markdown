# Python Operators Lesson

## Section 1 – Explanations

Python operators are special symbols or keywords used to perform operations on variables and values. The lesson covers various types of operators, including arithmetic, assignment, comparison, logical, identity, membership, and bitwise operators, as well as operator precedence. Below, I’ll explain each category clearly for beginners, using examples from the lesson where provided or creating simple, beginner-friendly examples where needed.

### Arithmetic Operators
Arithmetic operators perform basic mathematical operations on numeric values. They include:
- `+` (Addition): Adds two values.
- `-` (Subtraction): Subtracts one value from another.
- `*` (Multiplication): Multiplies two values.
- `/` (Division): Divides one value by another, resulting in a float.
- `%` (Modulus): Returns the remainder of division.
- `**` (Exponentiation): Raises a number to a power.
- `//` (Floor Division): Divides and rounds down to the nearest integer.

**Example (from the lesson)**:
```python
print(10 + 5)  # Outputs: 15
```

**Simple Example**:
```python
a = 20
b = 3
print(a + b)  # Outputs: 23
print(a - b)  # Outputs: 17
print(a * b)  # Outputs: 60
print(a / b)  # Outputs: 6.666...
print(a % b)  # Outputs: 2
print(a ** b) # Outputs: 8000
print(a // b) # Outputs: 6
```

### Assignment Operators
Assignment operators assign values to variables. They include the basic `=` operator and compound operators that combine assignment with arithmetic or bitwise operations.
- `=` assigns a value to a variable.
- `+=`, `-=`, `*=`, `/=`, `%=`, `//=`, `**=` modify a variable’s value by performing an operation and assigning the result.
- Bitwise assignment operators (`&=`, `|=`, `^=`, `>>=`, `<<=`) and the walrus operator (`:=`) are more advanced and will be covered lightly here for beginners.

**Example (from the lesson)**:
```python
x = 5  # Assigns 5 to x
x += 3 # Same as x = x + 3, so x becomes 8
print(x)  # Outputs: 8
```

**Simple Example**:
```python
score = 10
score += 5  # score is now 15
score *= 2  # score is now 30
print(score)  # Outputs: 30
```

### Comparison Operators
Comparison operators compare two values and return `True` or `False`.
- `==` (Equal): Checks if two values are equal.
- `!=` (Not equal): Checks if two values are not equal.
- `>`, `<`, `>=`, `<=` compare numerical values.

**Simple Example**:
```python
x = 10
y = 20
print(x == y)  # Outputs: False
print(x != y)  # Outputs: True
print(x < y)   # Outputs: True
print(x >= y)  # Outputs: False
```

### Logical Operators
Logical operators combine conditional statements:
- `and`: True if both conditions are true.
- `or`: True if at least one condition is true.
- `not`: Reverses the truth value.

**Example (from the lesson)**:
```python
x = 7
print(x < 5 and x < 10)  # Outputs: False (because x < 5 is False)
print(x < 5 or x < 10)   # Outputs: True (because x < 10 is True)
print(not(x < 5))        # Outputs: True (because x < 5 is False, so not False is True)
```

### Identity Operators
Identity operators check if two variables refer to the same object in memory:
- `is`: True if both variables are the same object.
- `is not`: True if they are not the same object.

**Simple Example**:
```python
a = [1, 2, 3]
b = a
c = [1, 2, 3]
print(a is b)    # Outputs: True (same object)
print(a is c)    # Outputs: False (different objects, same content)
print(a is not c) # Outputs: True
```

### Membership Operators
Membership operators test if a value is in a sequence (like a list or string):
- `in`: True if the value is found in the sequence.
- `not in`: True if the value is not found.

**Simple Example**:
```python
fruits = ["apple", "banana", "cherry"]
print("apple" in fruits)      # Outputs: True
print("orange" not in fruits) # Outputs: True
```

### Bitwise Operators
Bitwise operators work on binary representations of numbers. For beginners, it’s enough to know they manipulate numbers at the bit level (e.g., `&` for AND, `|` for OR). These are advanced and less commonly used in beginner programs, so we’ll skip detailed examples.

### Operator Precedence
Operator precedence determines the order in which operations are performed. Parentheses `()` have the highest precedence, followed by exponentiation `**`, multiplication/division, addition/subtraction, and so on. If operators have the same precedence, they are evaluated left to right.

**Example (from the lesson)**:
```python
print((6 + 3) - (6 + 3))  # Outputs: 0 (parentheses first: 9 - 9)
print(100 + 5 * 3)        # Outputs: 115 (5 * 3 = 15, then 100 + 15)
print(5 + 4 - 7 + 3)      # Outputs: 5 (evaluated left to right)
```

## Section 2 – Class Exercise

**Exercise: Calculate a Shopping Bill**

You’re shopping for groceries and need to calculate the total cost of items, apply a discount, and check if you have enough money to pay.

1. Create two variables for the prices of two items (e.g., `item1_price = 25` and `item2_price = 15`).
2. Use the addition operator (`+`) to calculate the total cost.
3. Apply a 10% discount using the multiplication operator (`*`) (hint: multiply by 0.9 to reduce the price by 10%).
4. Use a comparison operator to check if your budget (e.g., `budget = 35`) is enough to cover the discounted total.
5. Print the total cost, the discounted total, and whether you can afford the items.

**Step-by-Step Guidance**:
- Assign prices to two variables.
- Add the prices to get the total.
- Multiply the total by 0.9 to apply the discount.
- Use `>=` to compare the discounted total with your budget.
- Use `print()` to display the results.

## Section 3 – Weekly Project

**Project: Build a Simple Budget Checker**

You’re creating a program to help someone manage their weekly shopping budget. The program should calculate the total cost of items, check if they’re within budget, and suggest whether they can add another item.

**Project Brief**:
- Create variables for three item prices and a weekly budget (e.g., `budget = 100`).
- Calculate the total cost using the `+` operator.
- Use a comparison operator (`<=`) to check if the total is within the budget.
- If within budget, calculate how much money is left and suggest if they can afford an additional item (e.g., a snack costing $5).
- Use logical operators (`and` or `or`) to check if the remaining budget is enough and if the total is less than or equal to the budget.
- Print a message summarizing the total cost, whether it’s within budget, and whether they can afford the extra item.

**Step-by-Step Guidelines**:
1. Define variables for three item prices and a budget.
2. Calculate the total cost using addition.
3. Use `<=` to check if the total is within the budget.
4. Calculate the remaining budget using subtraction.
5. Use `and` to check if the remaining budget is enough for the extra item (e.g., `remaining >= 5 and total <= budget`).
6. Print clear messages, e.g., “Your total is $X. You are within budget!” or “You can afford a $5 snack!”.
7. Explore how to use `input()` to let users enter prices themselves (hint: this introduces a new concept for the next lesson!).

This project encourages combining operators while sparking curiosity about user input for dynamic programs.