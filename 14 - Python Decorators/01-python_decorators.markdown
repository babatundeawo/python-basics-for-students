# Python Decorators for Beginners

This tutorial covers Python decorators, which add extra behavior to functions without modifying their code. Below is a beginner-friendly teaching package based on the provided lesson note, designed to guide learners toward intermediate-level mastery with practical examples and exercises.

---

## Section 1 — Topical Explanations

### Learning Goals
- Understand how to define and apply decorators using the `@` syntax.
- Learn to handle arguments in decorated functions, including `*args` and `**kwargs`.
- Explore decorators with arguments and multiple decorators.
- Use `functools.wraps` to preserve function metadata.
- Emphasize decorators for adding reusable functionality without changing original code.

### Basic Decorator
A decorator is a function that takes another function as input, wraps it with additional behavior, and returns a new function. Use `@decorator_name` to apply it.

**Example Code**:
```python
# Define a decorator to uppercase the function's return value
def changecase(func):
    def myinner():
        return func().upper()  # Call original function and modify output
    return myinner

@changecase
def myfunction():
    return "Hello Sally"  # Outputs: HELLO SALLY

print(myfunction())
```
- **Line-by-Line Explanation**:
  - `def changecase(func):`: Defines decorator, takes function `func` as input.
    - **Input**: Function `func`.
    - **Output**: Wrapper function `myinner`.
  - `def myinner():`: Inner function that adds behavior.
  - `return func().upper()`: Calls original function, converts result to uppercase.
    - **Output**: Uppercase string.
  - `return myinner`: Returns wrapper function.
  - `@changecase`: Applies decorator to `myfunction`.
  - `def myfunction():`: Defines function returning `"Hello Sally"`.
  - `print(myfunction())`: Calls decorated function.
    - **Output**: `HELLO SALLY`.
- **Visual Description**: Terminal shows `HELLO SALLY` in uppercase.
- **Common Mistake**: Forgetting to return `myinner` in decorator.
  - **Error**: `TypeError` (NoneType not callable).
  - **Fix**: Ensure `return myinner`:
    ```python
    def changecase(func):
        def myinner():
            return func().upper()
        return myinner
    ```
- **Validation Check**: Verify output is uppercase. Call `myfunction()` multiple times to confirm consistency.

### Multiple Decorator Calls
Decorators can be applied to multiple functions using `@decorator_name`.

**Example Code**:
```python
def changecase(func):
    def myinner():
        return func().upper()
    return myinner

@changecase
def myfunction():
    return "Hello Sally"  # Outputs: HELLO SALLY

@changecase
def otherfunction():
    return "I am speed!"  # Outputs: I AM SPEED!

print(myfunction())
print(otherfunction())
```
- **Explanation**:
  - `changecase` is reused for both `myfunction` and `otherfunction`.
  - Each function’s return value is uppercased.
- **Common Mistake**: Incorrect decorator syntax (e.g., `@changecase()`).
  - **Error**: `TypeError` (function expected, not call result).
  - **Fix**: Use `@changecase` without parentheses.

### Arguments in Decorated Functions
Decorated functions can accept arguments by passing them through the wrapper.

**Example Code**:
```python
def changecase(func):
    def myinner(x):
        return func(x).upper()  # Pass argument to original function
    return myinner

@changecase
def myfunction(nam):
    return "Hello " + nam  # Outputs: HELLO JOHN

print(myfunction("John"))
```
- **Explanation**:
  - `myinner(x)`: Accepts argument `x`.
  - `func(x).upper()`: Passes `x` to original function, uppercases result.
  - **Input**: `nam` (string, e.g., `"John"`).
  - **Output**: `HELLO JOHN`.

### Using *args and **kwargs
`*args` and `**kwargs` allow decorators to handle any number or type of arguments.

**Example Code**:
```python
def changecase(func):
    def myinner(*args, **kwargs):
        return func(*args, **kwargs).upper()  # Pass all arguments
    return myinner

@changecase
def myfunction(nam):
    return "Hello " + nam  # Outputs: HELLO JOHN

print(myfunction("John"))
```
- **Explanation**:
  - `*args, **kwargs`: Collects all positional and keyword arguments.
  - `func(*args, **kwargs)`: Passes arguments to original function.
  - **Output**: Uppercase string.
- **Common Mistake**: Omitting `*args, **kwargs` for functions with arguments.
  - **Error**: `TypeError` (missing arguments).
  - **Fix**: Use `*args, **kwargs` in `myinner`.

### Decorator with Arguments
Decorators can accept their own arguments using a decorator factory (an outer function).

**Example Code**:
```python
def changecase(n):
    def decorator(func):
        def myinner():
            if n == 1:
                return func().lower()  # Lowercase if n=1
            else:
                return func().upper()  # Uppercase otherwise
        return myinner
    return decorator

@changecase(1)
def myfunction():
    return "Hello Linus"  # Outputs: hello linus

print(myfunction())
```
- **Explanation**:
  - `def changecase(n)`: Outer function (factory) takes argument `n`.
  - `def decorator(func)`: Middle function is the actual decorator.
  - `myinner()`: Inner function applies logic based on `n`.
  - `@changecase(1)`: Passes `n=1` to factory, selecting lowercase.
  - **Output**: `hello linus`.
- **Common Mistake**: Forgetting to return `decorator` in factory.
  - **Error**: `TypeError` (NoneType not callable).
  - **Fix**: Ensure `return decorator`.

### Multiple Decorators
Multiple decorators can be applied to a single function, executed in order from bottom to top.

**Example Code**:
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
    return "Tobias"  # Outputs: HELLO TOBIAS HAVE A GOOD DAY!

print(myfunction())
```
- **Explanation**:
  - `@addgreeting`: Applied first, adds greeting.
  - `@changecase`: Applied second, uppercases result.
  - Order: `myfunction` → `addgreeting` (`Hello Tobias Have a good day!`) → `changecase` (uppercase).
  - **Output**: `HELLO TOBIAS HAVE A GOOD DAY!`.
- **Common Mistake**: Misunderstanding decorator order.
  - **Fix**: Decorators execute bottom-up.

### Preserving Function Metadata
Decorators replace the original function, losing metadata like `__name__` and `__doc__`. Use `functools.wraps` to preserve them.

**Example Code (Without wraps)**:
```python
def changecase(func):
    def myinner():
        return func().upper()
    return myinner

@changecase
def myfunction():
    """Greets user."""
    return "Have a great day!"  # Outputs: myinner (not myfunction)

print(myfunction.__name__)
```
- **Output**: `myinner` (wrapper’s name).

**With wraps**:
```python
import functools

def changecase(func):
    @functools.wraps(func)
    def myinner():
        return func().upper()
    return myinner

@changecase
def myfunction():
    """Greets user."""
    return "Have a great day!"  # Outputs: myfunction

print(myfunction.__name__)
```
- **Explanation**:
  - `@functools.wraps(func)`: Copies metadata from `func` to `myinner`.
  - **Output**: `myfunction`.
- **Common Mistake**: Forgetting `functools.wraps`.
  - **Fix**: Import and apply `@functools.wraps`.

**One-Line Takeaway**: Python decorators enhance functions with reusable behavior, supporting arguments, multiple decorators, and metadata preservation with `functools.wraps`.

---

## Section 2 — Class Exercise

### Exercise: Text Formatter

**Objective**: Write a Python program that uses decorators to format text output from functions.

**Step-by-Step Instructions**:
1. Create a file named `text_formatter.py`.
2. Define:
   - A decorator `uppercase` to convert function output to uppercase.
   - A decorator `add_prefix(s)` to add a custom prefix to the output.
   - A function `greet(name)` to return a greeting.
   - A function `describe(*items)` to return a comma-separated list of items.
3. Apply decorators to both functions (e.g., `@uppercase` on `greet`, `@add_prefix("Items: ")` on `describe`).
4. Preserve metadata using `functools.wraps`.
5. Call functions with sample inputs.
6. Add comments to explain each step.
7. Run with `python text_formatter.py`.

**Hints**:
- Ensure `myinner` handles arguments with `*args, **kwargs`.
- Use `functools.wraps` to preserve function names.
- Test with different inputs to verify flexibility.

**Checkpoint**:
- Verify `greet` outputs uppercase (e.g., `HELLO JOHN`).
- Verify `describe` adds prefix (e.g., `Items: APPLE, BANANA`).
- Check `__name__` matches original function names.

**Example Output**:
```
Greet:
HELLO JOHN
Describe:
Items: APPLE, BANANA, CHERRY
Function Names:
greet
describe
```

---

## Section 3 — Weekly Project

### Project: Log Processor

**Objective**: Create a Python program that uses decorators to log function calls and process data.

**Milestones**:
1. Create a file named `log_processor.py`.
2. Define:
   - A decorator `log_call` to print function name and arguments before execution.
   - A decorator `time_call` to measure and print function execution time.
   - A function `sum_numbers(*numbers)` to return the sum of numbers.
   - A function `join_strings(*strings, **options)` to join strings with a separator.
3. Apply both decorators to each function.
4. Use `functools.wraps` to preserve metadata.
5. Validate inputs (e.g., numbers for `sum_numbers`, strings for `join_strings`).
6. Call functions with sample inputs.
7. Run with `python log_processor.py`.

**Deliverables**:
- A working `log_processor.py` file.
- Output showing logs, execution times, and results.

**Research Prompts**:
- How do decorators improve code modularity compared to inline modifications?
- Why is preserving function metadata important in production code?

**Assessment Criteria**:
- Code runs without errors.
- Decorators log calls and measure time correctly.
- Validation works.
- Output is clear and commented.
- Metadata is preserved.

**Extension Idea**:
- Add a decorator to count function calls.
- Log results to a file instead of printing.

**Example Output**:
```
Calling sum_numbers with args: (1, 2, 3), kwargs: {}
sum_numbers took 0.0001 seconds
Sum: 6
Calling join_strings with args: ('apple', 'banana'), kwargs: {'sep': '-'}
join_strings took 0.0002 seconds
Joined: apple-banana
All inputs valid
```

---

## Completion Checklist
- [ ] Understood decorator definition and application with `@`.
- [ ] Used `*args`, `**kwargs`, and decorator arguments.
- [ ] Applied multiple decorators and understood execution order.
- [ ] Preserved metadata with `functools.wraps`.
- [ ] Completed the class exercise and verified output.
- [ ] Started the weekly project and implemented log processor.
- [ ] Fixed at least one common mistake (e.g., missing `functools.wraps`).