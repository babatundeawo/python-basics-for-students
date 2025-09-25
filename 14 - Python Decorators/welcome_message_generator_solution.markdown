# Solution to the Weekly Project: Personalized Welcome Message Generator

This document provides the solution to the weekly project "Personalized Welcome Message Generator" from the Python Decorators lesson, tailored for complete beginners. The project involves creating a program that uses decorators to generate customized welcome messages for users signing into an app, combining decorators, functions with arguments, and string manipulation. Below, I’ll explain the solution step by step and provide the complete code, ensuring it’s clear, practical, and confidence-building.

---

## Explanation

The goal of the project is to build a welcome message generator that uses a decorator to add a customizable prefix (e.g., "Welcome!" or "Hi!") and a fixed suffix (e.g., "! Enjoy your stay!") to a user’s name. The program includes a function that takes a name and returns it, with the decorator enhancing the output. Additionally, the optional extension involves adding a second decorator to make the message uppercase and hints at using time-based suffixes (explored lightly to spark curiosity).

### Step-by-Step Breakdown
1. **Write the Decorator**:
   - Create a decorator factory called `add_welcome` that accepts a `prefix` argument (e.g., "Welcome!").
   - The decorator wraps a function, adding the prefix and a fixed suffix ("! Enjoy your stay!") to the function’s output.
   - For the optional extension, add a second decorator to convert the message to uppercase.

2. **Create the Core Function**:
   - Define a function called `greet_user` that takes a name as an argument and returns it.
   - Apply the `add_welcome` decorator to this function with a specific prefix.

3. **Test the Program**:
   - Test the decorated function with at least two names (e.g., "Linus", "Amina") and two prefixes (e.g., "Welcome!", "Hi!").
   - Verify that the output is formatted correctly (e.g., "Welcome! Linus! Enjoy your stay!").

4. **Optional Extension**:
   - Add a second decorator to make the entire message uppercase.
   - Explore a time-based suffix (e.g., "Good morning!" or "Good evening!") using Python’s `datetime` module, introducing beginners to a new concept gently.

### Solution Code
Below is the complete solution, including the basic requirements and the optional uppercase decorator. The time-based suffix is discussed but not fully implemented to keep it beginner-friendly while sparking curiosity.

```python
import functools

# Decorator factory to add a customizable prefix and fixed suffix
def add_welcome(prefix):
    def decorator(func):
        @functools.wraps(func)  # Preserve the original function's metadata
        def wrapper(name):
            return f"{prefix} {func(name)}! Enjoy your stay!"
        return wrapper
    return decorator

# Decorator to make the message uppercase
def make_uppercase(func):
    @functools.wraps(func)  # Preserve the original function's metadata
    def wrapper(name):
        return func(name).upper()
    return wrapper

# Core function to return the user's name
@make_uppercase  # Optional: Apply uppercase decorator
@add_welcome("Welcome!")  # Apply welcome decorator with "Welcome!" prefix
def greet_user(name):
    return name

# Test with different names and prefixes
print(greet_user("Linus"))  # Output: WELCOME! LINUS! ENJOY YOUR STAY!
print(greet_user("Amina"))  # Output: WELCOME! AMINA! ENJOY YOUR STAY!

# Test with a different prefix
@add_welcome("Hi!")  # Apply welcome decorator with "Hi!" prefix
def greet_user_alt(name):
    return name

print(greet_user_alt("Linus"))  # Output: Hi! Linus! Enjoy your stay!
print(greet_user_alt("Amina"))  # Output: Hi! Amina! Enjoy your stay!
```

### How It Works
- **Decorator Factory (`add_welcome`)**:
  - Takes a `prefix` argument (e.g., "Welcome!") to customize the message.
  - Returns a `decorator` function that wraps the original function (`func`).
  - The `wrapper` function takes a `name`, calls the original function (`func(name)`), and formats the output as `prefix + name + "! Enjoy your stay!"`.
  - Uses `functools.wraps` to preserve the original function’s metadata (e.g., `__name__`).

- **Uppercase Decorator (`make_uppercase`)**:
  - Takes a function (`func`) and returns a `wrapper` that converts the function’s output to uppercase using `.upper()`.
  - Applied as a second decorator to `greet_user` for the optional extension.
  - Also uses `functools.wraps` for metadata preservation.

- **Core Function (`greet_user`)**:
  - Simply returns the input `name`.
  - Decorated with `@make_uppercase` and `@add_welcome("Welcome!")`, so the output is first formatted (e.g., "Welcome! Linus! Enjoy your stay!") and then converted to uppercase (e.g., "WELCOME! LINUS! ENJOY YOUR STAY!").

- **Testing**:
  - Tests `greet_user` with "Linus" and "Amina" to show consistent formatting with the "Welcome!" prefix and uppercase output.
  - Tests `greet_user_alt` with a "Hi!" prefix to demonstrate prefix customization, without the uppercase decorator for variety.

### Optional Extension: Time-Based Suffix
For the time-based suffix, you could modify the `add_welcome` decorator to check the current time using Python’s `datetime` module. Here’s a conceptual example (kept simple to avoid overwhelming beginners):

```python
from datetime import datetime

def add_welcome(prefix):
    def decorator(func):
        @functools.wraps(func)
        def wrapper(name):
            hour = datetime.now().hour
            suffix = " Good morning!" if hour < 12 else " Good evening!"
            return f"{prefix} {func(name)}!{suffix}"
        return wrapper
    return decorator

@add_welcome("Welcome!")
def greet_user(name):
    return name

print(greet_user("Linus"))  # Output (e.g., at 11 AM): Welcome! Linus! Good morning!
```

- **Explanation**: The `datetime.now().hour` checks the current hour (0–23). If it’s before noon (`hour < 12`), the suffix is " Good morning!"; otherwise, it’s " Good evening!". This introduces beginners to `datetime` and conditionals, hinting at future lessons without requiring full implementation.

### Why This Solution Works
- **Simplicity**: The code uses clear, minimal examples that beginners can follow, with decorators doing one thing at a time (adding a prefix/suffix or uppercase).
- **Practicality**: The welcome message generator mimics real-world app features, like user greetings on a website, making it relatable.
- **Reinforcement**: Combines decorators, string formatting, and arguments, building on prior lessons (e.g., the name formatter exercise) while introducing `functools.wraps`.
- **Creativity**: The customizable prefix and optional uppercase decorator encourage experimentation, and the time-based suffix idea sparks curiosity about new modules.
- **Confidence-Building**: The structured milestones and clear outputs (e.g., "WELCOME! LINUS! ENJOY YOUR STAY!") show beginners they can create useful programs.

### Testing the Solution
- Run the main code to see outputs like:
  - `WELCOME! LINUS! ENJOY YOUR STAY!`
  - `WELCOME! AMINA! ENJOY YOUR STAY!`
  - `Hi! Linus! Enjoy your stay!`
  - `Hi! Amina! Enjoy your stay!`
- For the time-based extension, test at different times of day (e.g., morning vs. evening) to see the suffix change (if implemented).
- Experiment with other prefixes (e.g., "Hello!") or names to explore the decorator’s flexibility.

This solution provides a hands-on, practical way to master decorators while creating a fun, app-like feature. It balances simplicity with creativity, preparing beginners for more advanced topics like conditionals and modules.