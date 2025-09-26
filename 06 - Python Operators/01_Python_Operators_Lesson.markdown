# Python Operators for Complete Beginners

## Section 1 – Explanations

Operators in Python are like tools that let you perform actions on variables and values, such as adding numbers, comparing values, or combining conditions. They are the building blocks of many programs, helping you manipulate data in useful ways. Let’s break down the key types of operators covered in the lesson, focusing only on what’s provided, with clear and beginner-friendly explanations.

### Arithmetic Operators
These operators perform basic math operations on numbers. Think of them as a calculator for your code. Here’s a breakdown with a simple example:

```python
x = 10
y = 3
print(x + y)   # Addition: 13
print(x - y)   # Subtraction: 7
print(x * y)   # Multiplication: 30
print(x / y)   # Division: 3.333...
print(x % y)   # Modulus (remainder): 1
print(x ** y)  # Exponentiation (10^3): 1000
print(x // y)  # Floor division (division rounded down): 3
```

- **Addition (+)**: Adds two numbers, like `10 + 3 = 13`.
- **Subtraction (-)**: Subtracts one number from another, like `10 - 3 = 7`.
- **Multiplication (*)**: Multiplies numbers, like `10 * 3 = 30`.
- **Division (/)**: Divides numbers, giving a decimal result, like `10 / 3 = 3.333...`.
- **Modulus (%)**: Gives the remainder after division, like `10 % 3 = 1` (because 3 goes into 10 three times, leaving 1).
- **Exponentiation (**)**: Raises a number to a power, like `10 ** 3 = 1000` (10 cubed).
- **Floor Division (//)**: Divides and rounds down to the nearest whole number, like `10 // 3 = 3`.

These operators are useful for calculations, like totaling scores or splitting quantities.

### Assignment Operators
Assignment operators are used to store values in variables. The most common is `=`, which puts a value into a variable, like a labeled box. Others combine an operation with assignment.

```python
x = 5      # Assign 5 to x
x += 2     # Add 2 to x (same as x = x + 2), so x is now 7
x *= 3     # Multiply x by 3 (same as x = x * 3), so x is now 21
```

- `=`: Stores a value, like `x = 5`.
- `+=`: Adds and stores the result, like `x += 2` (adds 2 to x).
- `*=`: Multiplies and stores, like `x *= 3` (multiplies x by 3).
- Others like `-=`, `/=`, `%=`, `//=`, `**=` work similarly, combining math with assignment.

These are shortcuts to update variables efficiently.

### Comparison Operators
These compare two values and return `True` or `False`. They’re like asking questions about numbers or variables.

```python
a = 5
b = 3
print(a == b)  # Equal: False (5 is not equal to 3)
print(a != b)  # Not equal: True
print(a > b)   # Greater than: True
print(a < b)   # Less than: False
print(a >= b)  # Greater or equal: True
print(a <= b)  # Less or equal: False
```

- `==`: Checks if values are equal.
- `!=`: Checks if values are not equal.
- `>` and `<`: Check if one value is greater or less than another.
- `>=` and `<=`: Include equality in the comparison.

These are great for decision-making in programs, like checking if a score is high enough.

### Logical Operators
Logical operators combine `True` or `False` statements to make decisions, like combining rules.

```python
x = 4
print(x > 2 and x < 6)    # True (x is both greater than 2 and less than 6)
print(x > 5 or x < 6)     # True (x is less than 6, so one condition is true)
print(not (x > 5))        # True (reverses False to True)
```

- `and`: True if both conditions are true, like “is x between 2 and 6?”
- `or`: True if at least one condition is true, like “is x big or small?”
- `not`: Reverses the result, turning `True` to `False` or vice versa.

These help you combine multiple checks, like ensuring a password is long enough *and* contains a number.

### Identity Operators
These check if two variables point to the same object in memory, not just if their values are equal.

```python
x = [1, 2, 3]
y = x
z = [1, 2, 3]
print(x is y)      # True (x and y point to the same object)
print(x is z)      # False (x and z have same values but different objects)
print(x is not z)  # True
```

- `is`: True if both variables are the same object.
- `is not`: True if they are different objects.

This is less common for beginners but useful when checking if two variables share the same data.

### Membership Operators
These check if a value is inside a sequence, like a list or string.

```python
fruits = ["apple", "banana", "cherry"]
print("banana" in fruits)      # True
print("orange" not in fruits)  # True
```

- `in`: True if a value is found in the sequence.
- `not in`: True if a value is not found.

These are handy for searching, like checking if a user’s input is in a list of allowed options.

### Bitwise Operators
Bitwise operators work on binary numbers (0s and 1s). For beginners, think of them as advanced tools for manipulating numbers at the bit level. We’ll skip detailed binary math for now and focus on their purpose.

```python
x = 5  # Binary: 0101
y = 3  # Binary: 0011
print(x & y)  # AND: 1 (binary 0001)
print(x | y)  # OR: 7 (binary 0111)
print(x ^ y)  # XOR: 6 (binary 0110)
print(~x)     # NOT: -6 (inverts bits, complex for beginners)
print(x << 1) # Left shift: 10 (shifts bits left)
print(x >> 1) # Right shift: 2 (shifts bits right)
```

- `&` (AND): Sets a bit to 1 if both bits are 1.
- `|` (OR): Sets a bit to 1 if either bit is 1.
- `^` (XOR): Sets a bit to 1 if only one bit is 1.
- `~` (NOT): Flips all bits.
- `<<` and `>>`: Shift bits left or right, changing the number’s value.

For now, know these exist for low-level tasks like optimizing code or working with hardware.

### Operator Precedence
Precedence determines which operators run first, like in math where multiplication comes before addition. Parentheses `()` have the highest precedence, so use them to control the order.

```python
print((6 + 3) - (6 + 3))  # Parentheses first: 9 - 9 = 0
print(100 + 5 * 3)        # Multiplication first: 100 + 15 = 115
print(5 + 4 - 7 + 3)      # Left to right (same precedence): 5 + 4 = 9, 9 - 7 = 2, 2 + 3 = 5
```

Key rules:
- Parentheses `()` are always first.
- Exponentiation `**` comes next.
- Multiplication, division, modulus, floor division (`*, /, %, //`) are before addition and subtraction (`+, -`).
- Comparisons (`==, !=, >, <, >=, <=`), identity (`is, is not`), and membership (`in, not in`) come later.
- Logical operators (`not`, `and`, `or`) are last.
- If precedence is equal, go left to right.

This ensures your calculations happen in the right order, like solving `2 + 3 * 4` as `2 + 12 = 14`, not `20`.

These operators are the foundation of Python programming. As you practice, you’ll see how they combine to create powerful programs!

## Section 2 – Class Exercise

This exercise reinforces arithmetic, assignment, comparison, and logical operators in a practical way, connecting to variables and input/output from earlier lessons.

**Exercise: Build a Simple Budget Calculator**

Create a program that helps a user plan a small purchase:
1. Ask the user to input the price of an item (e.g., a book).
2. Ask the user to input their available budget.
3. Use comparison operators to check if they can afford the item (budget >= price).
4. Use arithmetic operators to calculate how much money they’ll have left after the purchase (budget - price).
5. Use logical operators to check if the purchase is reasonable (price is positive and budget is sufficient).
6. Print a message summarizing whether they can afford it and how much money will remain.

**Step-by-Step Guidance:**
- Use `input()` to get the price and budget as numbers (convert strings to `float` for decimals).
- Store the inputs in variables.
- Use `>=` to check if the budget is enough.
- Use `-` to calculate remaining money.
- Use `and` to ensure the price is positive (`> 0`) and the budget is sufficient.
- Print a clear message, like “You can afford it! You’ll have $X left.” or “Sorry, you need $X more.”

Try coding this step by step. Test it with different inputs, like a price of 15 and a budget of 20, or a price of 30 and a budget of 25. This will help you practice operators in a real-world context.

## Section 3 – Weekly Project

This project combines operators with variables, input/output, and basic decision-making, sparking curiosity about conditionals (a future topic).

**Weekly Project: Create a Fitness Goal Tracker**

Build a program to help someone track their daily exercise goals based on calories burned:
1. Ask the user to input the calories burned from three activities (e.g., running, cycling, swimming) as numbers.
2. Use arithmetic operators to calculate the total calories burned (`+`).
3. Use a comparison operator to check if the total meets or exceeds a goal of 500 calories (`>=`).
4. Use logical operators to check if all activities were performed (each calorie value is greater than 0).
5. Print a summary showing:
   - The total calories burned.
   - Whether the goal was met.
   - If all activities were done (using `and`).
6. Optional: Encourage creativity by letting the user add a feature, like calculating the average calories per activity (`/`).

**Project Brief and Milestones:**
- **Milestone 1**: Use `input()` to collect three calorie values and store them in variables (e.g., `run_calories`, `cycle_calories`, `swim_calories`).
- **Milestone 2**: Calculate the total using `+` and store it in a variable.
- **Milestone 3**: Use `>=` to check if the total is at least 500.
- **Milestone 4**: Use `and` to check if all three calorie values are greater than 0.
- **Milestone 5**: Print a clear message, like “Total: 600 calories, Goal met: Yes, All activities done: Yes.”
- **Stretch Goal**: Add a feature, like showing how many calories above or below the goal they are (`-`), or warn if any input is negative.

This project uses operators in a practical way, reinforces variables and input/output, and hints at conditionals for decision-making. Test it with different inputs to see how the results change, and feel free to add your own twist, like tracking a different goal!