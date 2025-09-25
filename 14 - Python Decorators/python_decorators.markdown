# Python Decorators for Beginners

Below is a structured lesson on Python decorators tailored for complete beginners. The lesson focuses solely on the concepts of decorators, with clear explanations, a class exercise, and a weekly project to reinforce learning.

---

## Section 1 – Explanations

**What are Decorators?**  
Decorators are a way to add extra behavior to a function without changing its code. Think of a decorator as a "wrapper" that takes a function, adds something to it (like a special effect), and returns a new version of the function. This is useful for reusing code or adding features like logging, timing, or modifying outputs.

**How Decorators Work**  
A decorator is a function that:
1. Takes another function as an argument.
2. Defines an inner function (often called a wrapper) that adds new behavior.
3. Returns the inner function to replace the original one.

You apply a decorator to a function using the `@decorator_name` syntax above the function definition.

**Example 1: Basic Decorator**  
Here’s a simple decorator that changes a function’s output to uppercase:

```python
def changecase(func):
    def myinner():
        return func().upper()  # Calls the original function and makes the result uppercase
    return myinner

@changecase
def myfunction():
    return "Hello Sally"

print(myfunction())  # Output: HELLO SALLY
```

- **Explanation**: 
  - `changecase` is the decorator. It takes a function (`func`) as input.
  - Inside `changecase`, the `myinner` function runs the original function (`func()`) and modifies its output using `.upper()`.
  - The `@changecase` syntax tells Python to wrap `myfunction` with `changecase`. When `myfunction()` is called, it runs `myinner`, which returns the uppercase result.

**Example 2: Decorators with Arguments**  
Functions that take arguments need the decorator’s inner function to accept those arguments. Here’s how:

```python
def changecase(func):
    def myinner(x):  # Inner function accepts an argument
        return func(x).upper()
    return myinner

@changecase
def myfunction(nam):
    return "Hello " + nam

print(myfunction("John"))  # Output: HELLO JOHN
```

- **Explanation**: The inner function `myinner` accepts the argument `x` (in this case, `"John"`) and passes it to the original function `func`. The result (`"Hello John"`) is converted to uppercase.

**Example 3: Using `*args` and `**kwargs`**  
To make a decorator flexible for any number of arguments, use `*args` (for positional arguments) and `**kwargs` (for keyword arguments):

```python
def changecase(func):
    def myinner(*args, **kwargs):
        return func(*args, **kwargs).upper()
    return myinner

@changecase
def myfunction(nam):
    return "Hello " + nam

print(myfunction("John"))  # Output: HELLO JOHN
```

- **Explanation**: `*args` and `**kwargs` allow the decorator to handle any arguments passed to the decorated function, making it reusable for functions with different inputs.

**Example 4: Multiple Decorators**  
You can stack multiple decorators on a single function. They are applied from bottom to top:

```python
def changecase(func):
    def myinner():
        return func().upper()
    return myinner

def addgreeting(func):
    def myinner():
        return "Hello " + func() + " Have a good day!"
    return myinner

@changecase
@addgreeting
def myfunction():
    return "Tobias"

print(myfunction())  # Output: HELLO TOBIAS HAVE A GOOD DAY!
```

- **Explanation**: 
  - `myfunction` is first wrapped by `addgreeting`, which adds `"Hello "` and `" Have a good day!"`.
  - Then, `changecase` makes the entire result uppercase.
  - The decorators are applied in order: `@addgreeting` first, then `@changecase`.

**Preserving Function Metadata**  
Functions have metadata like their name (`__name__`) or documentation (`__doc__`). Decorators replace the original function, which can overwrite this metadata. To preserve it, use `functools.wraps`:

```python
import functools

def changecase(func):
    @functools.wraps(func)  # Preserves the original function's metadata
    def myinner():
        return func().upper()
    return myinner

@changecase
def myfunction():
    return "Have a great day!"

print(myfunction.__name__)  # Output: myfunction
```

- **Explanation**: Without `functools.wraps`, the `__name__` would be `myinner` (the wrapper function’s name). Using `@functools.wraps(func)` keeps the original function’s name and documentation.

**Why This Matters**  
Decorators are like adding a reusable "upgrade" to your functions. They’re powerful because they let you add features (like uppercase text or greetings) without rewriting the original function, making your code cleaner and more flexible.

---

## Section 2 – Class Exercise

**Exercise: Build a Simple Name Formatter**  
Create a program that uses a decorator to format a user’s name with a title (like "Mr." or "Ms."). This exercise reinforces decorators, functions with arguments, and string manipulation, connecting to previous lessons on variables and string operations.

**Steps to Complete the Exercise**:
1. Write a decorator called `add_title` that takes a function and adds a title (e.g., "Mr.") before the function’s output.
2. Create a function called `get_name` that takes a name as an argument and returns it.
3. Use the `@add_title` decorator to wrap `get_name`.
4. Test your program by passing a name (e.g., "Amina") and printing the result (e.g., "Mr. Amina").
5. Bonus: Try modifying the decorator to accept an argument that lets you choose the title (e.g., "Mr." or "Ms.").

**Guidance**:
- Start by defining the decorator with an inner function that accepts an argument (the name).
- Inside the inner function, call the original function and add the title to its output.
- Use string concatenation (e.g., `"Mr. " + result`) to combine the title and name.
- Test with a simple name to make sure the output is formatted correctly.

This exercise helps you practice writing decorators and working with arguments, while creating a practical tool you might use in a real program (like formatting names for a contact list).

---

## Section 3 – Weekly Project

**Weekly Project: Personalized Welcome Message Generator**  
Create a program that uses decorators to generate customized welcome messages for users signing into an app. This project combines decorators, functions with arguments, and string manipulation, while encouraging creativity and hinting at future topics like user input and conditionals.

**Project Brief**:
Your task is to build a welcome message generator for an app. The program should:
- Use a decorator to add a cheerful prefix (e.g., "Welcome!") and suffix (e.g., "! Enjoy your stay!") to a user’s name.
- Allow the decorator to accept an argument to customize the prefix (e.g., "Hello!" or "Hi!").
- Create a function that takes a user’s name and returns it.
- Apply the decorator to the function and test it with different names and prefixes.

**Milestones**:
1. **Write the Decorator**:
   - Create a decorator factory (a function that takes an argument, like `prefix`, and returns a decorator).
   - The decorator should wrap a function and add the prefix and a fixed suffix (e.g., "! Enjoy your stay!") to the function’s output.
   - Example: If the prefix is "Welcome!" and the name is "Linus", the output should be "Welcome! Linus! Enjoy your stay!".

2. **Create the Core Function**:
   - Write a function called `greet_user` that takes a name as an argument and returns it.
   - Apply your decorator to this function.

3. **Test the Program**:
   - Test with at least two different names and two different prefixes (e.g., "Welcome!" and "Hi!").
   - Print the results to see the formatted messages.

4. **Extend the Project** (Optional):
   - Add a second decorator to make the entire message uppercase.
   - Try adding a feature where the suffix changes based on the time of day (e.g., "Good morning!" or "Good evening!"). Hint: You might need to explore how to get the current time in Python (a future topic!).

**Guidance**:
- Start by writing the decorator factory, which takes a `prefix` argument and returns a decorator function.
- Inside the decorator, define an inner function that accepts the name and combines it with the prefix and suffix.
- Test your function with simple inputs to ensure the decorator works.
- For the optional extension, experiment with stacking decorators or researching Python’s `datetime` module for time-based features.

**Why This Project?**  
This project mimics real-world scenarios, like formatting user messages in apps or websites. It reinforces decorators, encourages creative customization, and builds confidence in combining concepts. It also hints at future topics like conditionals (for time-based logic) and modules, sparking curiosity for what’s next.