# Solution to Lambda and Generator Practice Exercise

This document provides a solution to the **Lambda and Generator Practice** exercise from the Python Lambda, Recursion, and Generators teaching package. It includes the code, a detailed explanation, and verification of the expected outputs.

---

## Exercise Overview

**Objectives:**
- Use a lambda function with `map()` to square numbers in a list.
- Create a generator function to yield even numbers up to a given number.
- Combine both in a small task and verify the results.

**Tasks:**
1. Create a lambda function that squares a number (e.g., `x * x`).
2. Use `map()` to apply this lambda to the list `[1, 2, 3, 4, 5]` and print the result as a list.
3. Write a generator function `even_numbers(n)` that yields even numbers from 2 up to `n` (inclusive).
4. Use a for loop to print all even numbers up to 10 using the generator.

**Expected Outputs:**
- Task 1 & 2: `[1, 4, 9, 16, 25]`
- Task 3 & 4: `2, 4, 6, 8, 10` (each on a new line)

---

## Solution Code

```python
# Task 1 & 2: Lambda with map() to square numbers
numbers = [1, 2, 3, 4, 5]
squared = list(map(lambda x: x * x, numbers))
print("Squared numbers:", squared)

# Task 3: Generator function for even numbers
def even_numbers(n):
    num = 2
    while num <= n:
        if num % 2 == 0:
            yield num
        num += 1

# Task 4: Print even numbers up to 10 using the generator
print("Even numbers up to 10:")
for num in even_numbers(10):
    print(num)
```

---

## Explanation

### Task 1 & 2: Lambda with `map()` to Square Numbers

**Code Breakdown:**
- `numbers = [1, 2, 3, 4, 5]`: Defines the input list.
- `lambda x: x * x`: Creates a lambda function that takes a number `x` and returns its square (`x * x`).
- `map(lambda x: x * x, numbers)`: Applies the lambda to each element in `numbers`, producing a map object with squares (`1, 4, 9, 16, 25`).
- `list(map(...))`: Converts the map object to a list.
- `print("Squared numbers:", squared)`: Outputs the result with a label.

**Expected Output:**
```
Squared numbers: [1, 4, 9, 16, 25]
```

**Why It Works:**
- The lambda function is concise and directly computes the square of each number.
- `map()` efficiently applies the lambda to each list element.
- Converting the map object to a list makes the output readable.

**Common Pitfalls and Fixes:**
- **Pitfall**: Forgetting to convert `map()` to a list (e.g., `print(map(lambda x: x * x, numbers))` prints a map object).
  - **Fix**: Always use `list()` to get a list from `map()`.
- **Pitfall**: Incorrect lambda syntax (e.g., `lambda x x * x`).
  - **Fix**: Ensure proper syntax with a colon (`lambda x: x * x`).

**Validation Check:**
- The output `[1, 4, 9, 16, 25]` matches the checkpoint, as each number is squared (`1*1=1`, `2*2=4`, etc.).

### Task 3 & 4: Generator for Even Numbers

**Code Breakdown:**
- `def even_numbers(n)`: Defines a generator function that takes a number `n`.
- `num = 2`: Starts checking from 2, the first even number.
- `while num <= n`: Continues until `num` exceeds `n`.
- `if num % 2 == 0`: Checks if `num` is even.
- `yield num`: Yields the even number, pausing the function.
- `num += 1`: Increments `num` to check the next number.
- `for num in even_numbers(10)`: Iterates over the generator with `n = 10`, printing each yielded even number.

**Expected Output:**
```
Even numbers up to 10:
2
4
6
8
10
```

**Why It Works:**
- The generator yields only even numbers, saving memory by producing values one at a time.
- The `for` loop iterates over the generator, printing each value on a new line.
- The condition `num % 2 == 0` ensures only even numbers are yielded.

**Common Pitfalls and Fixes:**
- **Pitfall**: Yielding all numbers instead of just even ones (e.g., omitting `if num % 2 == 0`).
  - **Fix**: Include the even-number check to filter results.
- **Pitfall**: Forgetting to iterate over the generator (e.g., `print(even_numbers(10))` prints a generator object).
  - **Fix**: Use a `for` loop or `next()` to access yielded values.

**Validation Check:**
- The output `2, 4, 6, 8, 10` matches the checkpoint for `n = 10`.
- Testing with `next(even_numbers(10))` yields `2`, confirming the generator starts correctly.

---

## Running the Code

To run the code, save it as a Python file (e.g., `exercise.py`) and execute it in a Python environment. The output will show:
- The squared numbers as a list: `[1, 4, 9, 16, 25]`.
- The even numbers up to 10, each on a new line: `2, 4, 6, 8, 10`.

---

## Completion Checklist

- [x] Created a lambda function to square numbers.
- [x] Used `map()` to apply the lambda to `[1, 2, 3, 4, 5]`, producing `[1, 4, 9, 16, 25]`.
- [x] Wrote a generator function `even_numbers(n)` to yield even numbers.
- [x] Printed even numbers up to 10 using a for loop, producing `2, 4, 6, 8, 10`.
- [x] Verified outputs match the expected results.
- [x] Avoided common pitfalls like incorrect lambda syntax or forgetting to iterate the generator.

**One-Line Takeaway:**  
The exercise demonstrates how lambda functions with `map()` efficiently process lists and how generators yield values one at a time for memory-efficient iteration.