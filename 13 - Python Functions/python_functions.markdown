# Python Functions Lesson

## Section 1 – Explanations

A **function** in Python is a reusable block of code that performs a specific task and runs only when called. Functions help organize code, make it more modular, and reduce repetition. Below are explanations of the key concepts covered in the lesson, with examples.

1. **Creating and Calling a Function**  
   Use the `def` keyword to define a function, followed by the function name and parentheses `()`. The code block inside the function runs when the function is called by using its name followed by `()`.  
   **Example**:  
   ```python
   def my_function():
       print("Hello from a function")

   my_function()  # Output: Hello from a function
   ```

2. **Arguments and Parameters**  
   Functions can accept data called **arguments** (or args), which are passed into **parameters** (variables defined in the function). Parameters are listed in the parentheses during function definition, and arguments are provided when calling the function.  
   **Example**:  
   ```python
   def my_function(fname):
       print(fname + " Refsnes")

   my_function("Emil")  # Output: Emil Refsnes
   ```

3. **Number of Arguments**  
   A function must be called with the exact number of arguments it expects. For instance, a function with two parameters requires two arguments.  
   **Example**:  
   ```python
   def my_function(fname, lname):
       print(fname + " " + lname)

   my_function("Emil", "Refsnes")  # Output: Emil Refsnes
   # my_function("Emil")  # Error: missing 1 required argument
   ```

4. **Arbitrary Arguments (*args)**  
   Use `*args` to allow a function to accept any number of positional arguments, which are received as a tuple.  
   **Example**:  
   ```python
   def my_function(*kids):
       print("The youngest child is " + kids[2])

   my_function("Emil", "Tobias", "Linus")  # Output: The youngest child is Linus
   ```

5. **Keyword Arguments (kwargs)**  
   Arguments can be passed using `key=value` syntax, making the order of arguments irrelevant.  
   **Example**:  
   ```python
   def my_function(child3, child2, child1):
       print("The youngest child is " + child3)

   my_function(child1="Emil", child2="Tobias", child3="Linus")  # Output: The youngest child is Linus
   ```

6. **Arbitrary Keyword Arguments (**kwargs)**  
   Use `**kwargs` to accept any number of keyword arguments, which are received as a dictionary.  
   **Example**:  
   ```python
   def my_function(**kid):
       print("His last name is " + kid["lname"])

   my_function(fname="Tobias", lname="Refsnes")  # Output: His last name is Refsnes
   ```

7. **Default Parameter Value**  
   Parameters can have default values, used if no argument is provided.  
   **Example**:  
   ```python
   def my_function(country="Norway"):
       print("I am from " + country)

   my_function("Sweden")  # Output: I am from Sweden
   my_function()  # Output: I am from Norway
   ```

8. **Passing a List as an Argument**  
   Any data type (e.g., list, string, number) can be passed to a function and retains its type inside.  
   **Example**:  
   ```python
   def my_function(food):
       for x in food:
           print(x)

   fruits = ["apple", "banana", "cherry"]
   my_function(fruits)  # Output: apple, banana, cherry (one per line)
   ```

9. **Return Values**  
   Use the `return` statement to send a value back from a function.  
   **Example**:  
   ```python
   def my_function(x):
       return 5 * x

   print(my_function(3))  # Output: 15
   ```

10. **The pass Statement**  
    If a function has no content, use `pass` to avoid errors.  
    **Example**:  
    ```python
    def my_function():
        pass  # No error, function does nothing
    ```

11. **Positional-Only and Keyword-Only Arguments**  
    - Use `, /` to enforce positional-only arguments (no keyword arguments allowed).  
    - Use `*,` to enforce keyword-only arguments (no positional arguments allowed).  
    - Combine them for mixed argument types.  
    **Example**:  
    ```python
    def my_function(a, b, /, *, c, d):
        print(a + b + c + d)

    my_function(5, 6, c=7, d=8)  # Output: 26
    ```

12. **Recursion**  
    A function can call itself, useful for problems like calculating factorials or iterating through data. Be cautious to avoid infinite recursion.  
    **Example**:  
    ```python
    def tri_recursion(k):
        if k > 0:
            result = k + tri_recursion(k - 1)
            print(result)
        else:
            result = 0
        return result

    tri_recursion(6)  # Outputs: 1, 3, 6, 10, 15, 21
    ```

## Section 2 – Class Exercise

**Exercise: Create a Greeting Function**  
You run a small coffee shop and want to greet customers by name when they place an order. Write a function that takes a customer’s first name and prints a personalized greeting. Then, enhance it to include their order item (e.g., "coffee" or "tea") using a default parameter.

**Step-by-Step Guidance**:  
1. Define a function called `greet_customer` with two parameters: `name` (for the customer’s name) and `order` (with a default value of `"coffee"`).  
2. Inside the function, print a message like: `"Hello, [name]! Enjoy your [order]!"`.  
3. Call the function twice: once with just a name (e.g., `"Alice"`) and once with a name and order (e.g., `"Bob", "tea"`).  
4. Test what happens if you call the function with a keyword argument for `order`.  
5. Discuss with a partner: What happens if you forget to pass the `name` argument? How does the default parameter help?

## Section 3 – Weekly Project

**Project: Simple Budget Calculator**  
You’re building a program to help a student track their weekly expenses. Create a set of functions to calculate and display their total spending based on different categories (e.g., food, transport, entertainment). This project uses functions, arguments, default parameters, and return values to combine concepts from the lesson.

**Project Brief**:  
- **Goal**: Create a program with functions to calculate total weekly expenses and display a summary.  
- **Requirements**:  
  1. Write a function `add_expense(category, amount)` that takes a category (e.g., "food") and amount (e.g., 10.50) and returns the amount.  
  2. Write a function `weekly_summary(*expenses)` that accepts any number of expense amounts (using `*args`) and returns their total.  
  3. Write a function `display_summary(total, name="Student")` that prints a summary like: `"[name], your weekly total is $[total]."`. Use a default parameter for `name`.  
  4. In the main program, call `add_expense` for at least three categories, collect the amounts, pass them to `weekly_summary`, and display the result with `display_summary`.  
- **Steps to Get Started**:  
  1. Create the `add_expense` function to print a message like `"Added $[amount] for [category]."` and return the amount.  
  2. Create the `weekly_summary` function to sum all expenses passed to it.  
  3. Create the `display_summary` function to format and print the total.  
  4. Test the program with sample expenses (e.g., food=$20, transport=$15, entertainment=$10).  
  5. Experiment with calling `display_summary` with and without a custom name.  
- **Curiosity Spark**: Can you modify the `weekly_summary` function to also accept a dictionary of expenses using `**kwargs` (e.g., `food=20, transport=15`)? What might this let you do differently? (Hint: This will be useful for future lessons on dictionaries!)

This project encourages you to combine functions, arguments, and return values while exploring how to structure a small program. Be creative with how you present the summary to make it user-friendly!