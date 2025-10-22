# Python Lambda, Recursion, and Generators: Beginner-Friendly Teaching Package

This teaching package explains **Python Lambda Functions, Recursion, and Generators** in a beginner-friendly way, using clear examples, hands-on exercises, and a project to reinforce learning.

---

## Section 1 — Topical Explanations

### 1.1 Python Lambda Functions

**What are Lambda Functions?**  
A lambda function is a small, anonymous (unnamed) function in Python that can take any number of arguments but only has one expression. Think of it like a quick, one-line calculator for simple tasks. It’s useful when you need a function for a short time, like inside another function or with built-in tools like `map()`, `filter()`, or `sorted()`.

**Syntax:**  
```python
lambda arguments: expression
```
- **Arguments**: Inputs the function takes (e.g., `a`, `b`).
- **Expression**: A single operation that returns a result (e.g., `a + b`).

**Example 1: Basic Lambda Function**  
Let’s start with a simple lambda that adds 10 to a number.

```python
# Lambda function that adds 10 to an input
x = lambda a: a + 10
print(x(5))  # Input 5, output 15
```

**Line-by-Line Explanation:**
- `lambda a: a + 10`: Creates a function that takes `a` and returns `a + 10`.
- `x = lambda ...`: Stores the lambda function in variable `x`.
- `x(5)`: Calls the function with `a = 5`, computes `5 + 10`, and returns `15`.
- `print(x(5))`: Outputs `15` to the console.

**Expected Output:**
```
15
```

**Visual Description:**  
You’ll see `15` printed on the console, as the lambda adds 10 to the input 5.

**Common Mistakes:**
- Forgetting the colon (`:`) after arguments (e.g., `lambda a a + 10` → SyntaxError).
- Trying to include multiple expressions (e.g., `lambda a: a + 10; a * 2` → Invalid).

**Validation Check:**  
Try creating a lambda that subtracts 5 from a number. What’s the output for input `8`? (Answer: `3`)

**Example 2: Lambda with Multiple Arguments**  
Lambda functions can handle multiple inputs. Let’s multiply two numbers.

```python
# Lambda function that multiplies two numbers
x = lambda a, b: a * b
print(x(5, 6))  # Input 5 and 6, output 30
```

**Line-by-Line Explanation:**
- `lambda a, b: a * b`: Defines a function taking `a` and `b`, returning their product.
- `x(5, 6)`: Calls the function with `a = 5`, `b = 6`, computes `5 * 6`.
- `print(x(5, 6))`: Outputs `30`.

**Expected Output:**
```
30
```

**Why Use Lambda Functions?**  
Lambdas shine when used inside other functions or with tools like `map()`, `filter()`, or `sorted()`. They’re like a shortcut for writing small functions without naming them.

**Example 3: Lambda Inside a Function**  
Here’s a function that creates a lambda to multiply a number by a fixed value.

```python
# Function that returns a lambda
def myfunc(n):
    return lambda a: a * n

mydoubler = myfunc(2)  # Creates a lambda that doubles a number
print(mydoubler(11))   # Input 11, output 22
```

**Line-by-Line Explanation:**
- `def myfunc(n)`: Defines a function that takes `n`.
- `return lambda a: a * n`: Returns a lambda that multiplies input `a` by `n`.
- `mydoubler = myfunc(2)`: Sets `n = 2`, so the lambda becomes `lambda a: a * 2`.
- `mydoubler(11)`: Calls the lambda with `a = 11`, computes `11 * 2`, outputs `22`.

**Expected Output:**
```
22
```

**Lambda with Built-in Functions**  
Lambdas are often used with `map()`, `filter()`, and `sorted()` for concise code.

**Example 4: Using Lambda with `map()`**  
`map()` applies a function to every item in a list.

```python
# Double all numbers in a list
numbers = [1, 2, 3, 4, 5]
doubled = list(map(lambda x: x * 2, numbers))
print(doubled)
```

**Line-by-Line Explanation:**
- `lambda x: x * 2`: Defines a function that doubles `x`.
- `map(lambda x: x * 2, numbers)`: Applies the lambda to each number in `[1, 2, 3, 4, 5]`.
- `list(map(...))`: Converts the map object to a list `[2, 4, 6, 8, 10]`.
- `print(doubled)`: Outputs `[2, 4, 6, 8, 10]`.

**Expected Output:**
```
[2, 4, 6, 8, 10]
```

**Common Mistakes:**
- Forgetting to convert `map()` output to a list (e.g., `print(map(...))` prints a map object).
- Using incorrect syntax in the lambda (e.g., `lambda x x * 2` → SyntaxError).

**Validation Check:**  
What would `map(lambda x: x + 1, [1, 2, 3])` produce? (Answer: `[2, 3, 4]`)

**One-Line Takeaway:**  
Lambda functions are quick, one-line functions for simple tasks, especially useful with `map()`, `filter()`, and `sorted()`.

---

### 1.2 Python Recursion

**What is Recursion?**  
Recursion is when a function calls itself to solve a problem by breaking it into smaller pieces. Think of it like a set of nesting dolls: each doll opens to reveal a smaller one until you reach the smallest. Recursion needs a **base case** to stop and a **recursive case** to keep going.

**Example 1: Countdown Function**  
Let’s create a function that counts down from a number to 0.

```python
# Recursive countdown function
def countdown(n):
    if n <= 0:        # Base case
        print("Done!")
    else:             # Recursive case
        print(n)
        countdown(n - 1)

countdown(5)
```

**Line-by-Line Explanation:**
- `if n <= 0`: Base case—stops recursion when `n` is 0 or negative, prints “Done!”.
- `else: print(n)`: Prints the current number.
- `countdown(n - 1)`: Calls itself with `n - 1`, moving toward the base case.
- `countdown(5)`: Starts with `n = 5`, prints `5, 4, 3, 2, 1, Done!`.

**Expected Output:**
```
5
4
3
2
1
Done!
```

**Visual Description:**  
Each number appears on a new line, counting down from 5 to 1, followed by “Done!”.

**Common Mistakes:**
- Missing a base case (leads to infinite recursion and a stack overflow).
- Incorrectly updating the argument (e.g., `countdown(n)` instead of `n - 1`).

**Validation Check:**  
What happens if you call `countdown(3)`? (Answer: Prints `3, 2, 1, Done!`)

**Example 2: Factorial with Recursion**  
Factorial of `n` (n!) is the product of all numbers from 1 to `n`. For example, `5! = 5 * 4 * 3 * 2 * 1 = 120`.

```python
# Recursive factorial function
def factorial(n):
    if n == 0 or n == 1:  # Base case
        return 1
    else:                 # Recursive case
        return n * factorial(n - 1)

print(factorial(5))
```

**Line-by-Line Explanation:**
- `if n == 0 or n == 1`: Base case—returns 1 for `n = 0` or `n = 1`.
- `else: return n * factorial(n - 1)`: Multiplies `n` by the factorial of `n - 1`.
- `factorial(5)`: Computes `5 * factorial(4) = 5 * (4 * factorial(3)) = ... = 5 * 4 * 3 * 2 * 1 = 120`.

**Expected Output:**
```
120
```

**Common Mistakes:**
- Forgetting the base case (e.g., infinite recursion for negative `n`).
- Using incorrect base case (e.g., `if n == 0: return 0` gives wrong results).

**Validation Check:**  
What’s the output of `factorial(3)`? (Answer: `6`)

**One-Line Takeaway:**  
Recursion solves problems by breaking them into smaller, identical problems, but always needs a base case to avoid infinite loops.

---

### 1.3 Python Generators

**What are Generators?**  
Generators are like functions that can “pause” and “resume,” producing values one at a time. Imagine a vending machine that dispenses one item each time you press a button, instead of giving you everything at once. Generators use `yield` instead of `return` and are memory-efficient for large datasets.

**Example 1: Simple Generator**  
Let’s create a generator that yields numbers 1, 2, and 3.

```python
# Generator function
def my_generator():
    yield 1
    yield 2
    yield 3

for value in my_generator():
    print(value)
```

**Line-by-Line Explanation:**
- `def my_generator()`: Defines the generator function.
- `yield 1`, `yield 2`, `yield 3`: Pauses and returns each value one at a time.
- `for value in my_generator()`: Iterates over the generator, printing each yielded value.

**Expected Output:**
```
1
2
3
```

**Visual Description:**  
Each number (1, 2, 3) prints on a new line as the generator yields them.

**Common Mistakes:**
- Forgetting to iterate over the generator (e.g., `print(my_generator())` prints a generator object).
- Trying to reuse a generator after it’s exhausted (yields no more values).

**Validation Check:**  
What happens if you add `yield 4` to the generator? (Answer: Prints `1, 2, 3, 4`)

**Example 2: Generator with `next()`**  
You can manually control a generator using `next()`.

```python
# Generator with names
def simple_gen():
    yield "Emil"
    yield "Tobias"
    yield "Linus"

gen = simple_gen()
print(next(gen))  # First yield
print(next(gen))  # Second yield
print(next(gen))  # Third yield
```

**Line-by-Line Explanation:**
- `def simple_gen()`: Defines a generator yielding three names.
- `gen = simple_gen()`: Creates a generator object.
- `next(gen)`: Gets the next yielded value (`"Emil"`, then `"Tobias"`, then `"Linus"`).
- If `next()` is called again, it raises `StopIteration`.

**Expected Output:**
```
Emil
Tobias
Linus
```

**Common Mistakes:**
- Calling `next()` after the generator is exhausted (raises `StopIteration`).
- Not “priming” the generator with `next()` when using advanced methods like `send()`.

**Example 3: Generator Expression**  
Generator expressions are like list comprehensions but use `()` and don’t store the whole list in memory.

```python
# Generator expression for squares
gen_exp = (x * x for x in range(5))
print(list(gen_exp))
```

**Line-by-Line Explanation:**
- `(x * x for x in range(5))`: Creates a generator yielding squares (`0, 1, 4, 9, 16`).
- `list(gen_exp)`: Converts the generator to a list to print all values.
- `print(list(gen_exp))`: Outputs `[0, 1, 4, 9, 16]`.

**Expected Output:**
```
[0, 1, 4, 9, 16]
```

**One-Line Takeaway:**  
Generators produce values one at a time, saving memory for large datasets, using `yield` to pause and resume.

---

## Section 2 — Class Exercise

**Exercise: Lambda and Generator Practice**

**Objectives:**  
- Use a lambda function to process a list with `map()`.  
- Create a generator to yield even numbers.  
- Combine both in a small task.

**Step-by-Step Instructions:**  
1. Create a lambda function that squares a number (e.g., `x * x`).  
2. Use `map()` to apply this lambda to the list `[1, 2, 3, 4, 5]` and print the result as a list.  
3. Write a generator function `even_numbers(n)` that yields even numbers from 2 up to `n` (inclusive).  
4. Use a for loop to print all even numbers up to 10 using your generator.  

**Hints:**  
- For `map()`, convert the result to a list to see the output.  
- In the generator, use `if num % 2 == 0` to check for even numbers.  
- Test your generator with `next()` to get the first even number.

**Checkpoints:**  
- Does your lambda produce `[1, 4, 9, 16, 25]` for the given list?  
- Does your generator yield `2, 4, 6, 8, 10` for `n = 10`?  

---

## Section 3 — Weekly Project

**Project: Personal Budget Calculator**

**Overview:**  
Create a program that uses lambda functions, recursion, and generators to manage a simple budget. Users input expenses, and the program calculates totals and categorizes them.

**Milestones:**  
1. **Input Expenses:** Ask the user to input expenses (amount and category, e.g., “Food” or “Travel”) until they type “done”. Store them as a list of tuples `(amount, category)`.  
2. **Total Expenses (Recursion):** Write a recursive function to sum all expense amounts.  
3. **Category Filter (Lambda):** Use a lambda with `filter()` to list expenses in a specific category.  
4. **Expense Generator:** Create a generator to yield expenses one at a time for review.  

**Deliverables:**  
- A Python script that:  
  - Collects expenses.  
  - Calculates the total using recursion.  
  - Filters expenses by category using a lambda.  
  - Uses a generator to display expenses one by one.  
- A short comment explaining how each part works.

**Research Prompts:**  
- How does recursion compare to a loop for summing a list?  
- Why is a generator better than a list for reviewing large numbers of expenses?  
- How can lambda functions simplify code with `filter()`?

**Assessment Criteria:**  
- Correctly collects and stores expenses.  
- Recursive function correctly sums expenses.  
- Lambda function filters expenses by category.  
- Generator yields expenses one at a time.  
- Code runs without errors and is well-commented.

**Extension Ideas:**  
- Add a lambda with `sorted()` to sort expenses by amount.  
- Modify the generator to yield only expenses above a certain amount.  
- Use recursion to find the highest single expense.

---

## Completion Checklist

- [ ] Understood lambda function syntax and used it with `map()`.  
- [ ] Created and tested a recursive function with a clear base case.  
- [ ] Built a generator and iterated over it using `for` or `next()`.  
- [ ] Completed the class exercise and verified outputs.  
- [ ] Started the weekly project with at least one milestone completed.  
- [ ] Avoided common pitfalls like missing base cases or incorrect lambda syntax.  

**One-Line Takeaway Summary:**  
Lambda functions, recursion, and generators simplify Python code for quick calculations, repetitive tasks, and memory-efficient data processing.