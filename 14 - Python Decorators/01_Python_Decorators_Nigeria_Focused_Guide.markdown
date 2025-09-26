# Python Decorators: Nigeria-Focused Beginner’s Guide

This guide follows the **AI Instructional Framework for Teaching Python Beginners (Nigeria-Focused Edition)**. It covers the lesson note on Python decorators comprehensively, with clear explanations, a relatable class exercise, and a practical weekly project, all tailored to Nigerian contexts.

---

## Section 1 – Explanations

### What Are Decorators?
A decorator in Python is like adding a special wrapper to a gift (the function) to make it more exciting without changing the gift itself. It’s a function that takes another function as input, adds extra behavior, and returns a new function. Think of it as adding a “Buy One, Get One Free” deal to a recharge card purchase without changing how the card works.

The lesson note covers several aspects of decorators. Let’s break them down step-by-step, explaining each concept and example in detail, with Nigerian-themed analogies.

---

### 1. Basic Decorator
**Concept Explanation**: A decorator is a function that wraps another function to modify its behavior. The `@decorator_name` syntax is used to apply the decorator to a function. The decorator function defines a wrapper (inner function) that changes the output of the original function.

**Example from the Lesson**:
```python
def changecase(func):
  def myinner():
    return func().upper()
  return myinner

@changecase
def myfunction():
  return "Hello Sally"

print(myfunction())
```

**Line-by-Line Explanation**:
- `def changecase(func):`: Defines the decorator function `changecase`, which takes a function `func` as input. Think of `changecase` as a shopkeeper who takes your recharge card order and adds a bonus.
- `def myinner():`: The inner function `myinner` is the wrapper that will modify the behavior of the input function `func`. It’s like the shopkeeper’s process for adding the bonus.
- `return func().upper()`: Calls the original function `func()` (e.g., `myfunction`) and converts its result to uppercase using `.upper()`. Imagine the shopkeeper shouting your order loudly to make it stand out.
- `return myinner`: The decorator returns the wrapper function, which replaces the original function when called.
- `@changecase`: This applies the `changecase` decorator to `myfunction`. It’s like sticking a “Special Offer” sticker on your recharge card.
- `def myfunction():`: Defines a simple function that returns `"Hello Sally"`.
- `print(myfunction())`: Calls the decorated `myfunction`, which now returns `"HELLO SALLY"` in uppercase.

**Relatable Analogy**: Imagine you’re selling airtime at a market stall. Normally, you give the customer the airtime they paid for. With a decorator, you add a bonus (like extra data) without changing how you sell the airtime. The `@changecase` decorator is like shouting the customer’s name in uppercase to make it memorable.

---

### 2. Multiple Decorator Calls
**Concept Explanation**: You can apply the same decorator to multiple functions by placing `@decorator_name` above each function definition. Each function gets the same extra behavior.

**Example from the Lesson**:
```python
def changecase(func):
  def myinner():
    return func().upper()
  return myinner

@changecase
def myfunction():
  return "Hello Sally"

@changecase
def otherfunction():
  return "I am speed!"

print(myfunction())
print(otherfunction())
```

**Line-by-Line Explanation**:
- The `changecase` decorator is the same as before, converting the function’s output to uppercase.
- `@changecase` is applied to both `myfunction` (returns `"Hello Sally"`) and `otherfunction` (returns `"I am speed!"`).
- `print(myfunction())`: Outputs `"HELLO SALLY"`.
- `print(otherfunction())`: Outputs `"I AM SPEED!"`.

**Relatable Analogy**: Think of a teacher in a Nigerian classroom who decides to write every student’s name in uppercase on the board to make it bold and clear. Whether it’s Amina’s name or Chukwu’s name, the teacher applies the same “uppercase rule” to both. The `@changecase` decorator works the same way for different functions.

---

### 3. Arguments in the Decorated Function
**Concept Explanation**: If the function being decorated takes arguments, the decorator’s wrapper function must accept those arguments to pass them to the original function.

**Example from the Lesson**:
```python
def changecase(func):
  def myinner(x):
    return func(x).upper()
  return myinner

@changecase
def myfunction(nam):
  return "Hello " + nam

print(myfunction("John"))
```

**Line-by-Line Explanation**:
- `def changecase(func):`: The decorator takes a function `func` as input.
- `def myinner(x):`: The wrapper function now accepts an argument `x` to match the argument expected by `myfunction`.
- `return func(x).upper()`: Calls `func` with the argument `x` and converts the result to uppercase.
- `@changecase`: Applies the decorator to `myfunction`.
- `def myfunction(nam):`: Defines a function that takes a name (`nam`) and returns `"Hello " + nam`.
- `print(myfunction("John"))`: Calls the decorated function with `"John"`, returning `"HELLO JOHN"`.

**Relatable Analogy**: Imagine you’re ordering food at a buka (local eatery). You tell the server your name and the dish you want (e.g., “Amala for Tunde”). The decorator is like the server adding a loud announcement of your order in uppercase to make sure everyone hears it clearly. The argument (`nam`) is passed through the decorator to the function.

---

### 4. Using *args and **kwargs
**Concept Explanation**: To make decorators flexible for functions with any number or type of arguments, use `*args` (for positional arguments) and `**kwargs` (for keyword arguments) in the wrapper function.

**Example from the Lesson**:
```python
def changecase(func):
  def myinner(*args, **kwargs):
    return func(*args, **kwargs).upper()
  return myinner

@changecase
def myfunction(nam):
  return "Hello " + nam

print(myfunction("John"))
```

**Line-by-Line Explanation**:
- `def myinner(*args, **kwargs):`: The wrapper accepts any number of positional arguments (`*args`) and keyword arguments (`**kwargs`).
- `return func(*args, **kwargs).upper()`: Passes all arguments to `func` and converts the result to uppercase.
- The rest is similar to the previous example, outputting `"HELLO JOHN"`.

**Relatable Analogy**: Think of a market trader who can sell any item (e.g., yam, rice, or beans) to any customer, no matter how many items they order. The `*args` and `**kwargs` are like the trader’s ability to handle any order size or type, shouting the order in uppercase to confirm it.

---

### 5. Decorator with Arguments
**Concept Explanation**: A decorator can accept its own arguments by adding an outer layer, creating a “decorator factory.” This outer function takes the arguments and returns the actual decorator.

**Example from the Lesson**:
```python
def changecase(n):
  def changecase(func):
    def myinner():
      if n == 1:
        a = func().lower()
      else:
        a = func().upper()
      return a
    return myinner
  return changecase

@changecase(1)
def myfunction():
  return "Hello Linus"

print(myfunction())
```

**Line-by-Line Explanation**:
- `def changecase(n):`: The outer function (decorator factory) takes an argument `n` to decide the case (lowercase if `n == 1`, uppercase otherwise).
- `def changecase(func):`: The actual decorator takes the function `func`.
- `def myinner():`: The wrapper function processes the logic.
- `if n == 1: a = func().lower()`: If `n` is 1, convert the function’s output to lowercase.
- `else: a = func().upper()`: Otherwise, convert to uppercase.
- `return changecase`: The factory returns the decorator.
- `@changecase(1)`: Applies the decorator with `n = 1`, so the output will be lowercase.
- `print(myfunction())`: Outputs `"hello linus"`.

**Relatable Analogy**: Imagine a tailor in Lagos who can customize a dress based on your request. If you say “simple style” (like `n = 1`), the tailor makes it plain (lowercase). If you say “fancy style,” they add flair (uppercase). The decorator factory (`changecase(n)`) is like the tailor’s ability to take your customization request.

---

### 6. Multiple Decorators
**Concept Explanation**: You can stack multiple decorators on a single function. They are applied in order from bottom to top (the closest decorator to the function is applied first).

**Example from the Lesson**:
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

print(myfunction())
```

**Line-by-Line Explanation**:
- `def addgreeting(func):`: A decorator that adds `"Hello "` before and `" Have a good day!"` after the function’s output.
- `def changecase(func):`: The same uppercase decorator as before.
- `@changecase` and `@addgreeting`: Applied to `myfunction`. Since `@addgreeting` is closer to the function, it runs first, then `@changecase` modifies the result.
- Execution flow:
  1. `myfunction()` returns `"Tobias"`.
  2. `@addgreeting` wraps it to `"Hello Tobias Have a good day!"`.
  3. `@changecase` converts the result to `"HELLO TOBIAS HAVE A GOOD DAY!"`.
- `print(myfunction())`: Outputs the final result.

**Relatable Analogy**: Imagine preparing a plate of jollof rice. First, you add the rice and stew (`@addgreeting` adds the greeting). Then, you sprinkle extra spices to make it bold (`@changecase` makes it uppercase). The decorators work together to enhance the final dish.

---

### 7. Preserving Function Metadata
**Concept Explanation**: Functions have metadata like `__name__` (the function’s name) and `__doc__` (its docstring). Decorators replace the original function with the wrapper, which can change the metadata. The `functools.wraps` function preserves the original metadata.

**Examples from the Lesson**:
1. **Without Preserving Metadata**:
```python
def myfunction():
  return "Have a great day!"

print(myfunction.__name__)  # Outputs: myfunction
```
```python
def changecase(func):
  def myinner():
    return func().upper()
  return myinner

@changecase
def myfunction():
  return "Have a great day!"

print(myfunction.__name__)  # Outputs: myinner
```

2. **With Preserving Metadata**:
```python
import functools

def changecase(func):
  @functools.wraps(func)
  def myinner():
    return func().upper()
  return myinner

@changecase
def myfunction():
  return "Have a great day!"

print(myfunction.__name__)  # Outputs: myfunction
```

**Line-by-Line Explanation**:
- Without `functools.wraps`, the `__name__` attribute returns `"myinner"` (the wrapper’s name) instead of `"myfunction"`.
- `import functools`: Imports the `functools` module.
- `@functools.wraps(func)`: Preserves the original function’s metadata (e.g., name and docstring).
- With `functools.wraps`, `print(myfunction.__name__)` correctly outputs `"myfunction"`.

**Relatable Analogy**: Imagine labeling a bag of garri with your shop’s name. Without `functools.wraps`, the decorator is like putting a new label (“myinner”) that hides your shop’s name. With `functools.wraps`, you keep your shop’s original label (`myfunction`) visible, even after adding the decorator’s wrapper.

---

## Section 2 – Class Exercise

**Exercise: Airtime Recharge Formatter**

**Objective**: Create a program that formats an airtime recharge confirmation message using a decorator to make the message bold and exciting.

**Why It’s Fun**: Students can show off a program that mimics the kind of confirmation message they get when recharging their phone, making it relatable and something to share with friends.

**Connection to Lesson**: This exercise uses a basic decorator to modify the output of a function, reinforcing the concept of wrapping a function to add behavior.

**Step-by-Step Guidance**:
1. Create a function called `recharge_message` that takes a phone number (as a string) and returns a confirmation message like `"You have recharged N500 on 08012345678."`.
2. Define a decorator called `make_bold` that wraps the message in a bold style (for simplicity, add `***` before and after the message to represent bold text).
3. Apply the `@make_bold` decorator to `recharge_message`.
4. Test the function by calling `recharge_message("08012345678")` and printing the result.
5. Expected output: `***You have recharged N500 on 08012345678.***`

**Hints**:
- The decorator should look like `def make_bold(func):` with an inner function that modifies the output.
- Use string concatenation to add `***` to the start and end of the message.
- Make sure the inner function accepts the phone number argument.

This exercise is simple but practical, letting students create something they can relate to (like a real MTN or Glo recharge confirmation).

---

## Section 3 – Weekly Project

**Project: JAMB Score Announcement System**

**Objective**: Build a program that announces a student’s JAMB score with customizable formatting using decorators. The program should take a student’s name and score, then apply different decorators based on user input (e.g., uppercase for high scores, lowercase for encouragement).

**Why It’s Fun**: Nigerian students are familiar with JAMB exams, and creating a program that announces scores in a bold or encouraging way feels exciting and shareable. They can show it to friends and say, “I built a JAMB score announcer with Python!”

**Connection to Lesson**: This project combines basic decorators, decorators with arguments, and multiple decorators, while incorporating earlier concepts like input/output and conditionals.

**Project Brief**:
Create a program that:
1. Takes user input for the student’s name and JAMB score (0–400).
2. Uses a decorator factory to format the announcement based on the score:
   - If the score is 200 or above, use an uppercase decorator to announce it boldly.
   - If the score is below 200, use a lowercase decorator to make it encouraging.
3. Adds a second decorator to include a greeting like “Congratulations” or “Try again next time” based on the score.
4. Outputs the formatted announcement.

**Milestones**:
1. **Input Handling**: Use `input()` to get the student’s name and score. Convert the score to an integer.
2. **Decorator Factory**: Create a decorator factory `format_score(style)` that returns a decorator to make the output uppercase (`style = "bold"`) or lowercase (`style = "encouraging"`).
3. **Greeting Decorator**: Create a decorator `add_greeting` that adds “Congratulations” for scores ≥ 200 or “Try again next time” for scores < 200.
4. **Main Function**: Define a function `announce_score(name, score)` that returns a message like `"[name] scored [score] in JAMB."`.
5. **Logic**: Use conditionals to apply the appropriate decorators based on the score.
6. **Output**: Print the final announcement, e.g., `Congratulations [NAME] SCORED 250 IN JAMB. Have a great day!` or `Try again next time [name] scored 150 in jamb. Have a great day!`.

**Extensions**:
- Add a third decorator to include the school the student might attend based on the score (e.g., “Likely to attend UNILAG” for high scores).
- Allow the user to input multiple students and display their announcements.

**Guidance**:
- Start by writing the `announce_score` function.
- Create the `format_score` decorator factory to handle bold or encouraging styles.
- Write the `add_greeting` decorator to add the appropriate message.
- Use conditionals to decide which decorators to apply based on the score.
- Test with different names and scores to see the formatted output.

This project is practical, ties into the JAMB experience, and lets students create something they’ll be proud to share with peers.