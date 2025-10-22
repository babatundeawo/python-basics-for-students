# Solution to Python Weekly Project: Log Processor

This document provides the solution to the Python weekly project from the Python Decorators tutorial, where the task is to create a program that uses decorators to log function calls and process data. Below is the solution code, followed by a detailed explanation tailored for beginners.

---

## Solution Code

```python
# log_processor.py
# This program uses decorators to log function calls and measure execution time

"""
Program: Log Processor
Author: [Your Name]
Purpose: Demonstrates decorators for logging function calls and timing execution
"""

import functools
import time

# Decorator to log function name and arguments
def log_call(func):
    @functools.wraps(func)
    def wrapper(*args, **kwargs):
        print(f"Calling {func.__name__} with args: {args}, kwargs: {kwargs}")
        result = func(*args, **kwargs)
        return result
    return wrapper

# Decorator to measure execution time
def time_call(func):
    @functools.wraps(func)
    def wrapper(*args, **kwargs):
        start_time = time.time()
        result = func(*args, **kwargs)
        end_time = time.time()
        print(f"{func.__name__} took {end_time - start_time:.4f} seconds")
        return result
    return wrapper

# Function to sum numbers
@log_call
@time_call
def sum_numbers(*numbers):
    """Returns the sum of given numbers."""
    if not all(isinstance(num, (int, float)) for num in numbers):
        raise ValueError("All arguments must be numbers")
    return sum(numbers)

# Function to join strings with optional separator
@log_call
@time_call
def join_strings(*strings, **options):
    """Joins strings with a separator (default: space)."""
    if not all(isinstance(s, str) for s in strings):
        raise ValueError("All arguments must be strings")
    sep = options.get("sep", " ")
    return sep.join(strings)

# Main program
print("Log Processor:")
try:
    # Test sum_numbers
    result1 = sum_numbers(1, 2, 3)
    print(f"Sum: {result1}")

    # Test join_strings
    result2 = join_strings("apple", "banana", sep="-")
    print(f"Joined: {result2}")

    # Validate inputs
    print("All inputs valid")

except ValueError as e:
    print(f"Error: {e}")

# Verify metadata
print("Function Names:")
print(sum_numbers.__name__)
print(join_strings.__name__)
```

**Expected Output**:
```
Log Processor:
Calling sum_numbers with args: (1, 2, 3), kwargs: {}
sum_numbers took 0.0001 seconds
Sum: 6
Calling join_strings with args: ('apple', 'banana'), kwargs: {'sep': '-'}
join_strings took 0.0002 seconds
Joined: apple-banana
All inputs valid
Function Names:
sum_numbers
join_strings
```

---

## Explanation

### Objective
The project requires creating a Python program (`log_processor.py`) that:
- Defines a decorator `log_call` to print function name and arguments before execution.
- Defines a decorator `time_call` to measure and print function execution time.
- Defines a function `sum_numbers(*numbers)` to return the sum of numbers.
- Defines a function `join_strings(*strings, **options)` to join strings with a separator.
- Applies both decorators to each function.
- Uses `functools.wraps` to preserve metadata.
- Validates inputs (numbers for `sum_numbers`, strings for `join_strings`).
- Calls functions with sample inputs and verifies metadata.
- Runs correctly with `python log_processor.py`.

### Line-by-Line Breakdown
Let’s walk through the code to understand each part, its input, output, and purpose:

1. **File Creation**:
   - The code is saved in a file named `log_processor.py`. This ensures Python recognizes it as a Python script when you run `python log_processor.py`.

2. **Single-Line Comment**:
   ```python
   # log_processor.py
   # This program uses decorators to log function calls and measure execution time
   ```
   - **Purpose**: Describes the file and program purpose. Ignored by Python.
   - **Input**: None.
   - **Output**: None.
   - **Side Effects**: None.

3. **Multiline Comment**:
   ```python
   """
   Program: Log Processor
   Author: [Your Name]
   Purpose: Demonstrates decorators for logging function calls and timing execution
   """
   ```
   - **Purpose**: Provides detailed documentation. Ignored by Python since it’s not assigned.
   - **Input**: None.
   - **Output**: None.
   - **Side Effects**: None.

4. **Imports**:
   ```python
   import functools
   import time
   ```
   - **Purpose**: Imports `functools` for `wraps` to preserve metadata and `time` for measuring execution time.
   - **Input**: None.
   - **Output**: None.
   - **Side Effects**: Makes `functools.wraps` and `time.time` available.

5. **Decorator: log_call**:
   ```python
   def log_call(func):
       @functools.wraps(func)
       def wrapper(*args, **kwargs):
           print(f"Calling {func.__name__} with args: {args}, kwargs: {kwargs}")
           result = func(*args, **kwargs)
           return result
       return wrapper
   ```
   - **Purpose**: Logs function name and arguments before execution.
   - **Input**: `func` (function to decorate).
   - **Output**: Wrapper function that logs and calls `func`.
   - **Side Effects**: Prints log message.
   - **Explanation**:
     - `@functools.wraps(func)`: Preserves metadata of `func`.
     - `def wrapper(*args, **kwargs)`: Accepts any arguments.
     - `print(f"Calling {func.__name__}...")`: Logs function name and arguments.
     - `result = func(*args, **kwargs)`: Calls original function.
     - `return result`: Returns function output.

6. **Decorator: time_call**:
   ```python
   def time_call(func):
       @functools.wraps(func)
       def wrapper(*args, **kwargs):
           start_time = time.time()
           result = func(*args, **kwargs)
           end_time = time.time()
           print(f"{func.__name__} took {end_time - start_time:.4f} seconds")
           return result
       return wrapper
   ```
   - **Purpose**: Measures and prints function execution time.
   - **Input**: `func` (function to decorate).
   - **Output**: Wrapper function that times and calls `func`.
   - **Side Effects**: Prints execution time.
   - **Explanation**:
     - `start_time = time.time()`: Records start time.
     - `result = func(*args, **kwargs)`: Calls original function.
     - `end_time = time.time()`: Records end time.
     - `print(f"{func.__name__} took...")`: Prints time difference.
     - `return result`: Returns function output.

7. **Function: sum_numbers**:
   ```python
   @log_call
   @time_call
   def sum_numbers(*numbers):
       """Returns the sum of given numbers."""
       if not all(isinstance(num, (int, float)) for num in numbers):
           raise ValueError("All arguments must be numbers")
       return sum(numbers)
   ```
   - **Purpose**: Sums numbers, decorated to log and time execution.
   - **Input**: `*numbers` (variable number of numbers).
   - **Output**: Sum of numbers (e.g., `6` for `1, 2, 3`).
   - **Side Effects**: Raises `ValueError` for non-numbers.
   - **Explanation**:
     - `@log_call`: Logs call details.
     - `@time_call`: Times execution.
     - `isinstance(num, (int, float))`: Validates numeric inputs.
     - `sum(numbers)`: Returns sum.
     - Docstring documents function purpose.

8. **Function: join_strings**:
   ```python
   @log_call
   @time_call
   def join_strings(*strings, **options):
       """Joins strings with a separator (default: space)."""
       if not all(isinstance(s, str) for s in strings):
           raise ValueError("All arguments must be strings")
       sep = options.get("sep", " ")
       return sep.join(strings)
   ```
   - **Purpose**: Joins strings with a separator, decorated to log and time execution.
   - **Input**: `*strings` (variable strings), `**options` (e.g., `sep="-"`).
   - **Output**: Joined string (e.g., `apple-banana`).
   - **Side Effects**: Raises `ValueError` for non-strings.
   - **Explanation**:
     - `@log_call`, `@time_call`: Apply logging and timing.
     - `isinstance(s, str)`: Validates string inputs.
     - `sep = options.get("sep", " ")`: Uses default separator if none provided.
     - `sep.join(strings)`: Joins strings with separator.

9. **Main Program**:
   ```python
   print("Log Processor:")
   try:
       result1 = sum_numbers(1, 2, 3)
       print(f"Sum: {result1}")
       result2 = join_strings("apple", "banana", sep="-")
       print(f"Joined: {result2}")
       print("All inputs valid")
   except ValueError as e:
       print(f"Error: {e}")
   print("Function Names:")
   print(sum_numbers.__name__)
   print(join_strings.__name__)
   ```
   - **Purpose**: Demonstrates decorated functions and metadata.
   - **Explanation**:
     - `try/except`: Handles validation errors.
     - `sum_numbers(1, 2, 3)`: Outputs log, time, and sum (`6`).
     - `join_strings("apple", "banana", sep="-")`: Outputs log, time, and joined string (`apple-banana`).
     - `print("All inputs valid")`: Confirms valid inputs.
     - `sum_numbers.__name__, join_strings.__name__`: Outputs `sum_numbers`, `join_strings`.

### Visual Description
When you run `python log_processor.py` in the terminal, the output is:
```
Log Processor:
Calling sum_numbers with args: (1, 2, 3), kwargs: {}
sum_numbers took 0.0001 seconds
Sum: 6
Calling join_strings with args: ('apple', 'banana'), kwargs: {'sep': '-'}
join_strings took 0.0002 seconds
Joined: apple-banana
All inputs valid
Function Names:
sum_numbers
join_strings
```
Each section shows function call logs, execution times, results, and preserved function names. Times may vary slightly but are formatted to four decimal places.

### Common Mistakes and Fixes
1. **Forgetting `functools.wraps`**:
   - **Mistake**:
     ```python
     def log_call(func):
         def wrapper(*args, **kwargs):
             print(f"Calling {func.__name__} with args: {args}, kwargs: {kwargs}")
             return func(*args, **kwargs)
         return wrapper
     ```
   - **Error**: `sum_numbers.__name__` returns `wrapper` instead of `sum_numbers`.
   - **Fix**: Add `@functools.wraps(func)`:
     ```python
     def log_call(func):
         @functools.wraps(func)
         def wrapper(*args, **kwargs):
             print(f"Calling {func.__name__} with args: {args}, kwargs: {kwargs}")
             return func(*args, **kwargs)
         return wrapper
     ```
2. **Missing `*args, **kwargs` in Wrapper**:
   - **Mistake**:
     ```python
     def time_call(func):
         def wrapper():
             start_time = time.time()
             result = func()
             end_time = time.time()
             print(f"{func.__name__} took {end_time - start_time:.4f} seconds")
             return result
         return wrapper
     ```
   - **Error**: `TypeError` when `sum_numbers(1, 2, 3)` expects arguments.
   - **Fix**: Use `*args, **kwargs`:
     ```python
     def wrapper(*args, **kwargs):
         start_time = time.time()
         result = func(*args, **kwargs)
         end_time = time.time()
     ```
3. **Incorrect Decorator Order**:
   - **Mistake**: Swapping `@log_call` and `@time_call`.
   - **Error**: Logs may appear after timing, disrupting output order.
   - **Fix**: Apply `@log_call` above `@time_call` (executes bottom-up).
4. **Missing Input Validation**:
   - **Mistake**:
     ```python
     def sum_numbers(*numbers):
         return sum(numbers)
     ```
   - **Error**: Non-numeric inputs cause `TypeError` in `sum`.
   - **Fix**: Add validation:
     ```python
     if not all(isinstance(num, (int, float)) for num in numbers):
         raise ValueError("All arguments must be numbers")
     ```
5. **Wrong File Extension**:
   - **Mistake**: Saving as `log_processor.txt`.
   - **Fix**: Save as `log_processor.py` and run with `python log_processor.py`.

### Validation Check
To confirm the program works:
1. Save the code in `log_processor.py`.
2. Open a terminal, navigate to the file’s directory, and run `python log_processor.py`.
3. Verify the output matches: logs, times, `Sum: 6`, `Joined: apple-banana`, and function names `sum_numbers`, `join_strings`.
4. Test with invalid inputs (e.g., `sum_numbers(1, "two")`):
   - Should output `Error: All arguments must be numbers`.
5. Test with empty inputs (e.g., `join_strings()`):
   - Should output empty string with log and time.
6. Add `print(sum_numbers.__doc__)` to confirm docstring preservation (`Returns the sum of given numbers.`).

### Extension Idea Implementation
For learners interested in the extension ideas:
- **Count Calls Decorator**:
  ```python
  def count_calls(func):
      @functools.wraps(func)
      def wrapper(*args, **kwargs):
          wrapper.call_count += 1
          print(f"{func.__name__} call count: {wrapper.call_count}")
          return func(*args, **kwargs)
      wrapper.call_count = 0
      return wrapper
  ```
  - Add to `sum_numbers` (e.g., `@count_calls` above `@log_call`).
  - Outputs: `sum_numbers call count: 1` on first call, increments with each call.
- **Log to File**:
  ```python
  def log_call(func):
      @functools.wraps(func)
      def wrapper(*args, **kwargs):
          with open("log.txt", "a") as f:
              f.write(f"Calling {func.__name__} with args: {args}, kwargs: {kwargs}\n")
          return func(*args, **kwargs)
      return wrapper
  ```
  - Replace `print` with file write. Creates/appends to `log.txt`.

### Research Prompts Answered
- **How do decorators improve code modularity compared to inline modifications?**
  - Decorators separate concerns (e.g., logging, timing) from core logic, allowing reuse across functions without modifying their code. Inline modifications (e.g., adding `print` statements in `sum_numbers`) clutter the function and are not reusable.
- **Why is preserving function metadata important in production code?**
  - Metadata like `__name__` and `__doc__` is used in debugging, documentation, and tools like help(). Losing metadata (e.g., showing `wrapper` instead of `sum_numbers`) can confuse developers and break automated systems.

### One-Line Takeaway
This program uses decorators with `functools.wraps` to log and time function calls, with input validation, demonstrating modular and reusable code enhancements.