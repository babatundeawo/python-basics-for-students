# **Python Functions: Nigeria-Focused Python Lesson**

Below is a comprehensive response to the lesson note on **Python Functions**, tailored to beginners in a Nigerian context, following the provided instructional framework. The response is divided into three sections: **Explanations**, **Class Exercise**, and **Weekly Project**, ensuring clarity, relatability, and engagement.

---

## **Section 1 – Explanations**

This section explains the concepts from the lesson note on Python functions, breaking them down step-by-step with beginner-friendly language, relatable Nigerian examples, and thorough code explanations. Each concept is tied to the lesson note, and examples are either expanded or created where necessary.

### **What is a Function?**
A function is like a **recipe** for a task in Python. It’s a block of code that only runs when you call it, like telling a chef to cook *jollof rice* only when you’re ready to eat. You can give the function specific ingredients (data) to work with, and it can give you back a result, like serving you a plate of food.

### **Creating and Calling a Function**
To create a function, you use the `def` keyword, followed by the function’s name and parentheses `()`. The code inside the function runs only when you *call* it by writing its name with parentheses.

**Example from the Lesson Note:**
```python
def my_function():
    print("Hello from a function")

my_function()
```

**Explanation:**
- `def my_function():` creates a function named `my_function`. Think of it like naming a recipe “Jollof Rice Instructions.”
- `print("Hello from a function")` is the task the function performs, like saying “Serve jollof rice.”
- `my_function()` calls the function, telling Python to execute the code inside. When run, it prints: `Hello from a function`.
- In a Nigerian context, this is like shouting “Aunty, bring the food!” and the kitchen responds by serving the meal.

### **Arguments (Passing Data to Functions)**
Functions can take inputs called **arguments** to work with specific data, like giving a tailor the measurements for your *agbada*. Arguments are listed inside the parentheses when defining the function.

**Example from the Lesson Note:**
```python
def my_function(fname):
    print(fname + " Refsnes")

my_function("Emil")
my_function("Tobias")
my_function("Linus")
```

**Explanation:**
- `def my_function(fname):` defines a function with one parameter, `fname`, which acts like a placeholder for a name.
- `print(fname + " Refsnes")` combines the input name (`fname`) with the string `" Refsnes"` to form a full name.
- Calling `my_function("Emil")` passes `"Emil"` as the argument, so it prints `Emil Refsnes`. Similarly, `"Tobias"` prints `Tobias Refsnes`, and `"Linus"` prints `Linus Refsnes`.
- In a Nigerian context, this is like a teacher calling out names from a class register: “Chukwuma Okeke,” “Aisha Mohammed,” etc. The function takes each student’s first name and adds a family name to it.

### **Parameters vs. Arguments**
- A **parameter** is the variable in the function definition (e.g., `fname` in `def my_function(fname):`).
- An **argument** is the actual value you pass when calling the function (e.g., `"Emil"` in `my_function("Emil")`).
- Think of it like a market list: the list has a placeholder for “vegetables” (parameter), but you buy *ugu* or *spinach* (argument) when you go shopping.

### **Number of Arguments**
Functions expect the exact number of arguments they’re defined to take. If a function expects two arguments, you must provide two—not more, not less.

**Example from the Lesson Note:**
```python
def my_function(fname, lname):
    print(fname + " " + lname)

my_function("Emil", "Refsnes")
```

**Explanation:**
- `def my_function(fname, lname):` defines a function with two parameters: `fname` and `lname`.
- `print(fname + " " + lname)` combines the first name, a space, and the last name to print a full name.
- `my_function("Emil", "Refsnes")` passes `"Emil"` as `fname` and `"Refsnes"` as `lname`, printing `Emil Refsnes`.
- If you call `my_function("Emil")` with only one argument, Python will throw an error, like a Nigerian bus conductor refusing to move until all seats are filled correctly.

### **Arbitrary Arguments (*args)**
If you don’t know how many arguments will be passed, use `*args` to accept any number of arguments as a tuple.

**Example from the Lesson Note:**
```python
def my_function(*kids):
    print("The youngest child is " + kids[2])

my_function("Emil", "Tobias", "Linus")
```

**Explanation:**
- `def my_function(*kids):` uses `*kids` to accept any number of arguments, stored as a tuple named `kids`.
- `kids[2]` accesses the third item in the tuple (indexing starts at 0, so `kids[2]` is the third argument).
- Calling `my_function("Emil", "Tobias", "Linus")` passes three arguments, and `kids[2]` is `"Linus"`, so it prints `The youngest child is Linus`.
- In a Nigerian context, this is like a teacher calling out names from a list of students in a class, but only announcing the third student’s name as the “class captain.”

### **Keyword Arguments (kwargs)**
You can pass arguments using `key=value` syntax, so the order doesn’t matter.

**Example from the Lesson Note:**
```python
def my_function(child3, child2, child1):
    print("The youngest child is " + child3)

my_function(child1="Emil", child2="Tobias", child3="Linus")
```

**Explanation:**
- `def my_function(child3, child2, child1):` defines a function with three parameters.
- `my_function(child1="Emil", child2="Tobias", child3="Linus")` uses keyword arguments, so Python knows `child3="Linus"` regardless of the order.
- It prints `The youngest child is Linus`.
- This is like filling out a JAMB form where you specify “First Name = Chukwuma” and “Last Name = Okeke”—the order of the fields doesn’t matter as long as you label them correctly.

### **Arbitrary Keyword Arguments (**kwargs)**
If you don’t know how many keyword arguments will be passed, use `**kwargs` to accept them as a dictionary.

**Example from the Lesson Note:**
```python
def my_function(**kid):
    print("His last name is " + kid["lname"])

my_function(fname="Tobias", lname="Refsnes")
```

**Explanation:**
- `def my_function(**kid):` uses `**kid` to accept any number of keyword arguments, stored as a dictionary.
- `kid["lname"]` accesses the value associated with the key `"lname"` in the dictionary.
- `my_function(fname="Tobias", lname="Refsnes")` passes two keyword arguments, so `kid` is `{"fname": "Tobias", "lname": "Refsnes"}`. It prints `His last name is Refsnes`.
- In a Nigerian context, this is like a market trader keeping a record of a customer’s order: “Item = Garri, Price = 500”. The function picks out the price (like `lname`) to display.

### **Default Parameter Value**
You can set default values for parameters, used if no argument is provided.

**Example from the Lesson Note:**
```python
def my_function(country="Norway"):
    print("I am from " + country)

my_function("Sweden")
my_function("India")
my_function()
my_function("Brazil")
```

**Explanation:**
- `def my_function(country="Norway"):` sets a default value of `"Norway"` for `country`.
- `my_function("Sweden")` prints `I am from Sweden` because an argument is provided.
- `my_function()` uses the default, printing `I am from Norway`.
- This is like a Nigerian food vendor assuming you want *chin-chin* if you don’t specify a snack, but serving *puff-puff* if you ask for it.

### **Passing a List as an Argument**
You can pass a list to a function, and it remains a list inside the function.

**Example from the Lesson Note:**
```python
def my_function(food):
    for x in food:
        print(x)

fruits = ["apple", "banana", "cherry"]
my_function(fruits)
```

**Explanation:**
- `def my_function(food):` accepts a parameter `food`, which can be a list.
- `for x in food:` loops through each item in the list and prints it.
- `fruits = ["apple", "banana", "cherry"]` creates a list, and `my_function(fruits)` passes it to the function, printing:
  ```
  apple
  banana
  cherry
  ```
- In a Nigerian context, this is like listing items in a market basket: *yam*, *plantain*, *fish*. The function reads out each item one by one.

### **Return Values**
Functions can return results using the `return` statement.

**Example from the Lesson Note:**
```python
def my_function(x):
    return 5 * x

print(my_function(3))
print(my_function(5))
print(my_function(9))
```

**Explanation:**
- `def my_function(x):` defines a function that takes one parameter, `x`.
- `return 5 * x` multiplies `x` by 5 and sends the result back.
- `print(my_function(3))` calls the function with `x=3`, returns `15`, and prints it. Similarly, `my_function(5)` returns `25`, and `my_function(9)` returns `45`.
- In a Nigerian context, this is like a shopkeeper calculating the total cost of 5 packs of *Indomie* at ₦100 each: `5 * 100 = ₦500`.

### **The pass Statement**
If a function is empty, use `pass` to avoid errors.

**Example from the Lesson Note:**
```python
def myfunction():
    pass
```

**Explanation:**
- `def myfunction():` defines an empty function.
- `pass` is a placeholder that does nothing, preventing Python from throwing an error.
- This is like reserving a spot for a market stall but not setting it up yet—you’re just holding the space.

### **Positional-Only Arguments**
You can force arguments to be positional (not keyword) by adding `, /` after the parameters.

**Example from the Lesson Note:**
```python
def my_function(x, /):
    print(x)

my_function(3)
```

**Explanation:**
- `def my_function(x, /):` makes `x` a positional-only argument.
- `my_function(3)` works, printing `3`.
- `my_function(x=3)` would cause an error because keyword arguments are not allowed.
- This is like a Nigerian bus conductor insisting you say “Oshodi” (positionally) instead of labeling it as “destination=Oshodi.”

### **Keyword-Only Arguments**
You can force arguments to be keyword-only by adding `*,` before the parameters.

**Example from the Lesson Note:**
```python
def my_function(*, x):
    print(x)

my_function(x=3)
```

**Explanation:**
- `def my_function(*, x):` makes `x` a keyword-only argument.
- `my_function(x=3)` works, printing `3`.
- `my_function(3)` would cause an error because positional arguments are not allowed.
- This is like a school form requiring you to write “Age = 15” instead of just “15.”

### **Combining Positional-Only and Keyword-Only**
You can mix both types in one function.

**Example from the Lesson Note:**
```python
def my_function(a, b, /, *, c, d):
    print(a + b + c + d)

my_function(5, 6, c=7, d=8)
```

**Explanation:**
- `a` and `b` are positional-only (before `/`).
- `c` and `d` are keyword-only (after `*,`).
- `my_function(5, 6, c=7, d=8)` adds `5 + 6 + 7 + 8`, printing `26`.
- This is like a Nigerian caterer needing exact measurements for *rice* and *beans* (positional) but specific labels for *salt* and *oil* (keyword).

### **Recursion**
A function can call itself, called **recursion**, useful for repeating tasks.

**Example from the Lesson Note:**
```python
def tri_recursion(k):
    if k > 0:
        result = k + tri_recursion(k - 1)
        print(result)
    else:
        result = 0
    return result

print("Recursion Example Results:")
tri_recursion(6)
```

**Explanation:**
- `def tri_recursion(k):` defines a recursive function with parameter `k`.
- `if k > 0:` checks if `k` is positive.
- `result = k + tri_recursion(k - 1)` adds `k` to the result of calling the function with `k-1`.
- When `k = 0`, it returns `0`, stopping the recursion.
- For `tri_recursion(6)`:
  - `k=6`: `6 + tri_recursion(5)`
  - `k=5`: `5 + tri_recursion(4)`
  - `k=4`: `4 + tri_recursion(3)`
  - `k=3`: `3 + tri_recursion(2)`
  - `k=2`: `2 + tri_recursion(1)`
  - `k=1`: `1 + tri_recursion(0)`
  - `k=0`: returns `0`
  - Then: `1 + 0 = 1`, `2 + 1 = 3`, `3 + 3 = 6`, `4 + 6 = 10`, `5 + 10 = 15`, `6 + 15 = 21`.
- Output:
  ```
  Recursion Example Results:
  1
  3
  6
  10
  15
  21
  ```
- In a Nigerian context, this is like calculating the total cost of buying *suya* for 6 friends, where each friend’s portion includes the cost of the previous friends’ portions.

---

## **Section 2 – Class Exercise**

**Exercise: Build a “Market Price Announcer”**

This exercise uses functions, arguments, and return values to create a program that feels practical and exciting for Nigerian students. It builds on basic concepts like variables and printing, previously learned.

**Objective:**
Create a function that takes the name of a market item and its price, then announces the price in a friendly way, like a market trader calling out to customers.

**Steps to Guide Students:**
1. Define a function called `announce_price` that takes two parameters: `item` (the name of the product) and `price` (the cost in Naira).
2. Inside the function, create a message that combines the item and price, e.g., “Fresh tomatoes cost ₦500 only!”
3. Use the `return` statement to send this message back.
4. Call the function with different items and prices (e.g., “Yam”, 1200; “Fish”, 2000).
5. Print the returned messages to see the announcements.

**Why It’s Fun:**
Students can show off a program that mimics a lively Nigerian market trader, something they can proudly share with friends.

**Expected Output (Example):**
```
Fresh tomatoes cost ₦500 only!
Big yam costs ₦1200 only!
Fresh fish costs ₦2000 only!
```

**Guidance (No Full Solution):**
- Use `def` to create the function.
- Combine strings using `+` or an f-string (e.g., `f"Fresh {item} costs ₦{price} only!"`).
- Test with at least three different items and prices.
- If you want, add a default price (e.g., `price=100`) for when no price is given.

---

## **Section 3 – Weekly Project**

**Project: Build a “School Fee Payment Calculator”**

This project combines functions, arguments, return values, and conditionals (if previously learned) to create a practical tool that Nigerian students will find relatable and exciting to share.

**Project Brief:**
Create a program that calculates the total school fees for a student based on their class level and any extra fees (e.g., for books or uniforms). The program should use a function to compute the fees and return the result in a clear message.

**Milestones:**
1. **Define a Function**: Create a function called `calculate_fees` that takes two parameters:
   - `class_level` (e.g., “JSS1”, “JSS2”, “SS1”).
   - `extra_fees` (a number for additional costs, with a default value of `0`).
2. **Set Fee Structure**: Use conditionals (if learned) or simple logic to assign fees based on `class_level`:
   - JSS1: ₦20,000
   - JSS2: ₦22,000
   - JSS3: ₦25,000
   - SS1: ₦30,000
   - SS2: ₦32,000
   - SS3: ₦35,000
3. **Calculate Total**: Add `extra_fees` to the base fee and return a message like: “Total fees for JSS1 with ₦5000 extra is ₦25000.”
4. **Test the Function**: Call the function with different class levels and extra fees (e.g., `calculate_fees("JSS1", 5000)`, `calculate_fees("SS3")`).
5. **Extension (Optional)**: Add a keyword-only argument for a discount (e.g., `discount=2000`) and subtract it from the total.

**Why It’s Exciting:**
This project feels like a real tool a school bursar might use, and students can boast, “I built a fee calculator for my school!” It’s practical and sparks conversations among peers.

**Expected Output (Example):**
```
Total fees for JSS1 with ₦5000 extra is ₦25000.
Total fees for SS3 with ₦0 extra is ₦35000.
Total fees for JSS2 with ₦3000 extra is ₦25000.
```

**Guidance (No Full Solution):**
- Use `def` to create the function with `class_level` and `extra_fees=0`.
- Use `if-elif` (if learned) to check `class_level` and assign the correct fee.
- Combine the base fee and `extra_fees` in a `return` statement.
- Test with at least three different calls, including one with the default `extra_fees`.
- For the extension, add a `*, discount=0` parameter and subtract it from the total.

---

This response covers the entire lesson note on Python functions, using clear explanations, Nigerian-themed examples, and engaging activities that make learning fun and practical for beginners. Students will feel confident and proud to share their “Market Price Announcer” and “School Fee Payment Calculator” with friends!