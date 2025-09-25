# Solution to Movie Ticket Price Exercise

## Explanation

The exercise requires creating a Python program for a movie theater that calculates ticket prices based on a person’s age. The ticket prices are:
- $10 for kids (age 12 or under)
- $15 for adults (age 13–64)
- $8 for seniors (age 65 or older)

The program uses `input()` to get the user’s age, converts it to an integer with `int()`, and uses `if`, `elif`, and `else` statements to check the age against the specified ranges. Comparison operators (`<=`, `>=`) are used to determine which price category applies. The program then prints the appropriate ticket price.

The solution below includes error handling for non-numeric inputs using a `try-except` block to make the program more robust, though this goes slightly beyond the lesson’s scope to ensure a practical implementation. The explanation focuses only on the concepts from the lesson (if statements, comparison operators, and input).

### Solution Code

```python
age = input("Enter your age: ")

try:
    age = int(age)
    if age <= 12:
        print("Ticket price: $10")
    elif age >= 13 and age <= 64:
        print("Ticket price: $15")
    else:
        print("Ticket price: $8")
except ValueError:
    print("Please enter a valid number for age.")
```

### How It Works
1. **Input**: The program prompts the user to enter their age using `input()`, storing it in the `age` variable as a string.
2. **Conversion**: The `try` block converts the input to an integer using `int(age)`. If the input isn’t a valid number, the `except` block catches the error and prints a message.
3. **Conditionals**:
   - The `if` checks if `age <= 12` (kids). If true, it prints "$10".
   - The `elif` checks if `age >= 13 and age <= 64` (adults). If true, it prints "$15".
   - The `else` handles all other cases (seniors, age >= 65), printing "$8".
4. **Output**: The program prints the ticket price based on the age category.

### Example Runs
- **Input**: `10` → **Output**: `Ticket price: $10` (kid)
- **Input**: `30` → **Output**: `Ticket price: $15` (adult)
- **Input**: `70` → **Output**: `Ticket price: $8` (senior)
- **Input**: `abc` → **Output**: `Please enter a valid number for age.` (error handling)

This solution uses `if-elif-else` and comparison operators (`<=`, `>=`, `and`) from the lesson to determine the ticket price, making it simple and beginner-friendly while introducing basic error handling for robustness.