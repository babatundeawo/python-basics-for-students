# Solution to the Class Exercise: Simple Name Formatter

This document provides the solution to the class exercise "Build a Simple Name Formatter" from the Python Decorators lesson, along with a clear explanation for beginners. The exercise involves creating a decorator that adds a title (e.g., "Mr.") to a user’s name, reinforcing decorators, functions with arguments, and string manipulation. Below, I’ll explain the solution step by step and provide the complete code.

---

## Explanation

The goal of the exercise is to create a decorator called `add_title` that adds a title (like "Mr.") to the output of a function that returns a name. The function, `get_name`, takes a name as input and returns it. The decorator will wrap this function to add the title, and we’ll test it with a sample name. Additionally, the bonus task asks for a decorator that accepts an argument to choose the title (e.g., "Mr." or "Ms.").

### Step-by-Step Breakdown
1. **Define the Decorator**:
   - A decorator is a function that takes another function as input and returns a new function with added behavior.
   - For the basic solution, `add_title` will take a function (`func`), define an inner function that accepts a name, and add a fixed title (e.g., "Mr.") to the function’s output.
   - For the bonus solution, we’ll create a decorator factory that accepts a `title` argument (e.g., "Mr." or "Ms.") and returns a decorator.

2. **Create the Core Function**:
   - The `get_name` function takes a name (a string) as an argument and returns it.
   - This is the function we’ll decorate to add the title.

3. **Apply the Decorator**:
   - Use the `@add_title` syntax above `get_name` to apply the decorator.
   - For the bonus, we’ll use `@add_title("Mr.")` or `@add_title("Ms.")` to specify the title.

4. **Test the Program**:
   - Call the decorated `get_name` function with a sample name (e.g., "Amina") and print the result.
   - For the bonus, test with different titles to ensure flexibility.

### Solution Code (Basic Version)
Here’s the basic solution that adds a fixed "Mr." title:

```python
def add_title(func):
    def wrapper(name):
        return "Mr. " + func(name)  # Add "Mr." to the function’s output
    return wrapper

@add_title
def get_name(name):
    return name

# Test the decorated function
print(get_name("Amina"))  # Output: Mr. Amina
```

- **How It Works**:
  - The `add_title` decorator takes a function (`func`) as input.
  - The inner `wrapper` function accepts a `name` argument, calls the original function (`func(name)`), and adds "Mr. " to the result.
  - The `@add_title` syntax wraps `get_name` so that calling `get_name("Amina")` runs the `wrapper` function, which returns `"Mr. Amina"`.

### Solution Code (Bonus Version)
Here’s the bonus solution that allows choosing the title (e.g., "Mr." or "Ms."):

```python
def add_title(title):  # Decorator factory that accepts a title argument
    def decorator(func):  # The actual decorator
        def wrapper(name):  # Inner function that accepts the name
            return title + " " + func(name)  # Add the chosen title
        return wrapper
    return decorator

@add_title("Mr.")  # Specify the title
def get_name(name):
    return name

@add_title("Ms.")  # Specify a different title
def get_name_female(name):
    return name

# Test the decorated functions
print(get_name("Amina"))  # Output: Mr. Amina
print(get_name_female("Amina"))  # Output: Ms. Amina
```

- **How It Works**:
  - `add_title` is a decorator factory that takes a `title` argument (e.g., "Mr." or "Ms.").
  - It returns a `decorator` function that takes the original function (`func`) as input.
  - The `wrapper` function accepts the `name`, calls the original function (`func(name)`), and adds the specified `title` followed by a space.
  - By using `@add_title("Mr.")` and `@add_title("Ms.")`, we can apply different titles to different functions.
  - Testing with `get_name("Amina")` and `get_name_female("Amina")` shows how the decorator customizes the output.

### Why This Solution Works
- **Simplicity**: The basic version uses a straightforward decorator, making it easy for beginners to understand how decorators wrap functions.
- **Flexibility**: The bonus version introduces a decorator factory, showing how to customize decorators with arguments, which is a common real-world use case.
- **Practicality**: Adding titles to names mimics real-world applications, like formatting names in a contact management system.
- **Reinforcement**: The solution builds on prior concepts (functions, strings, and arguments) while introducing decorators, helping beginners connect new and old knowledge.

### Testing the Solution
- For the basic version, running `print(get_name("Amina"))` outputs `"Mr. Amina"`.
- For the bonus version, running `print(get_name("Amina"))` outputs `"Mr. Amina"`, and `print(get_name_female("Amina"))` outputs `"Ms. Amina"`.
- You can test with other names (e.g., `"John"`, `"Linus"`) or titles (e.g., `"Dr."`, `"Prof."`) to see the decorator’s flexibility.

This solution provides a hands-on way to practice decorators while creating a useful tool. It encourages experimentation (e.g., trying different titles) and builds confidence in applying decorators to real problems.