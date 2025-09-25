# Python If ... Else Lesson

## Section 1 – Explanations

The lesson covers Python's **if statements**, which allow programs to make decisions based on conditions. These conditions use logical operators from mathematics, such as `==` (equals), `!=` (not equals), `<` (less than), `<=` (less than or equal to), `>` (greater than), and `>=` (greater than or equal to). These are used to compare values and execute code blocks based on whether the condition is `True` or `False`.

An **if statement** starts with the `if` keyword, followed by a condition and a colon (`:`). The code block under it (indented with spaces) runs if the condition is true. Python relies on **indentation** (usually 4 spaces) to define the scope of the code block, unlike other languages that use curly braces. For example:

```python
a = 33
b = 200
if b > a:
    print("b is greater than a")
```

Here, since `b` (200) is greater than `a` (33), the message "b is greater than a" is printed. Without proper indentation, Python raises an error.

The **elif** keyword (short for "else if") checks another condition if the previous `if` or `elif` condition is false. For example:

```python
a = 33
b = 33
if b > a:
    print("b is greater than a")
elif a == b:
    print("a and b are equal")
```

Since `a` equals `b`, the `elif` block runs, printing "a and b are equal".

The **else** keyword handles cases not covered by `if` or `elif`. For example:

```python
a = 200
b = 33
if b > a:
    print("b is greater than a")
elif a == b:
    print("a and b are equal")
else:
    print("a is greater than b")
```

Here, since `a` (200) is greater than `b` (33), the `else` block runs.

**Short-hand if** and **short-hand if-else** (ternary operators) allow single-line conditionals. For example:

```python
a = 2
b = 330
if a > b: print("a is greater than b")
print("A") if a > b else print("B")
```

The first line checks if `a > b` and prints if true. The second line prints "A" if `a > b`, else "B". Multiple conditions can be combined in a single line:

```python
a = 330
b = 330
print("A") if a > b else print("=") if a == b else print("B")
```

Logical operators like **and**, **or**, and **not** combine or modify conditions. For example:

```python
a = 200
b = 33
c = 500
if a > b and c > a:
    print("Both conditions are True")
```

Here, both `a > b` and `c > a` must be true for the message to print.

**Nested if** statements allow conditions within conditions:

```python
x = 41
if x > 10:
    print("Above ten,")
    if x > 20:
        print("and also above 20!")
    else:
        print("but not above 20.")
```

If `x > 10` is true, the inner `if` checks if `x > 20`. Since both are true, both messages print.

The **pass** statement is a placeholder for empty `if` blocks to avoid errors:

```python
if b > a:
    pass
```

The **match** statement (Python 3.10+) is an alternative to multiple `if-else` statements. It compares an expression to multiple cases and executes the matching block:

```python
day = 4
match day:
    case 1:
        print("Monday")
    case 4:
        print("Thursday")
```

Here, `day = 4` matches `case 4`, printing "Thursday". A default case uses `_`:

```python
match day:
    case 6:
        print("Saturday")
    case _:
        print("Not Saturday")
```

The **pipe operator (`|`)** combines values in a `match` case:

```python
match day:
    case 1 | 2 | 3 | 4 | 5:
        print("Weekday")
```

**If guards** in `match` add extra conditions:

```python
month = 5
day = 4
match day:
    case 1 | 2 | 3 | 4 | 5 if month == 5:
        print("A weekday in May")
```

## Section 2 – Class Exercise

### Exercise: Determine Movie Ticket Price

You’re building a program for a movie theater that calculates ticket prices based on age. Create a program that takes a person’s age as input and prints their ticket price: $10 for kids (age 12 or under), $15 for adults (age 13–64), and $8 for seniors (age 65 or older).

**Guidelines:**
1. Ask the user to input their age using `input()`.
2. Use `if`, `elif`, and `else` to check the age ranges.
3. Print the appropriate ticket price based on the age.
4. Test your program with different ages (e.g., 10, 30, 70).
5. Hint: Convert the input to an integer using `int()` and use comparison operators (`<=`, `>=`).

## Section 3 – Weekly Project

### Project: Simple Weather Advisor

Create a program that advises users on what to wear based on the weather. The program should take two inputs: the temperature (in Celsius) and whether it’s raining (yes or no). Based on these, suggest an outfit using `if-elif-else` or a `match` statement.

**Project Brief:**
- **Inputs**: Temperature (e.g., 25 for 25°C) and rain status ("yes" or "no").
- **Rules**:
  - If temperature is below 10°C, suggest a "heavy jacket".
  - If temperature is 10–20°C, suggest a "light jacket".
  - If temperature is above 20°C, suggest a "t-shirt".
  - If it’s raining, add "and bring an umbrella" to the suggestion.
- **Output**: Print a message like "Wear a t-shirt and bring an umbrella."

**Guidelines:**
1. Use `input()` to get the temperature and rain status.
2. Convert the temperature input to an integer with `int()`.
3. Use `if-elif-else` or a `match` statement to evaluate the temperature and rain status.
4. Combine conditions using `and` for the rain check.
5. Test with different inputs (e.g., 5°C with rain, 25°C without rain).
6. **Curiosity Spark**: Research how to handle invalid inputs (e.g., non-numeric temperature) to make your program more robust. This introduces input validation, a useful concept for future lessons.

This project encourages combining conditions and logical operators while sparking interest in error handling.