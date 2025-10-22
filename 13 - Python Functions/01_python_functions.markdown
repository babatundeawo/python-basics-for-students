# Python Functions for Beginners

This tutorial covers Python functions, including defining and calling functions, arguments (`*args`, `**kwargs`), return values, scope (local, global, nonlocal), and the LEGB rule. Below is a beginner-friendly teaching package based on the provided lesson note, designed to guide learners toward intermediate-level mastery with practical examples and exercises.

---

## Section 1 — Topical Explanations

### Learning Goals
- Understand how to define and call functions using the `def` keyword.
- Learn to use arguments (positional, keyword, default, `*args`, `**kwargs`) and return values.
- Explore scope (local, global, nonlocal) and the LEGB rule.
- Use the `pass` statement for function placeholders.
- Emphasize functions to avoid code repetition and improve reusability.

### Creating and Calling a Function
A function is a reusable block of code that runs when called, defined using the `def` keyword. Indentation defines the function body.

**Example Code**:
```python
# Define and call a function
def greet():
    print("Hello from a function")  # Outputs: Hello from a function

greet()
greet()  # Can be called multiple times
```
- **Line-by-Line Explanation**:
  - `def greet():`: Defines a function named `greet`. **Input**: None. **Output**: None. **Side Effects**: Creates function.
  - `print("Hello from a function")`: Prints message when called. **Output**: `Hello from a function`.
  - `greet()`: Calls the function. **Output**: Message printed.
- **Visual Description**: Terminal shows `Hello from a function` each time `greet()` is called.
- **Common Mistake**: Missing indentation in function body.
  - **Error**: `IndentationError`.
  - **Fix**: Indent with 4 spaces:
    ```python
    def greet():
        print("Hello from a function")
    ```
- **Validation Check**: Call `greet()` multiple times to confirm repeated output.

### Function Names
Function names follow variable naming rules: start with a letter or underscore, contain only letters, numbers, or underscores, and are case-sensitive. Use descriptive names.

**Example Code**:
```python
def calculate_sum():  # Valid, descriptive name
    pass

def _private_function():  # Valid, private convention
    pass

def myFunction2():  # Valid, mixed case
    pass
```
- **Explanation**: Names like `calculate_sum` are clear; `myfunction` and `myFunction` are different.
- **Common Mistake**: Using invalid characters, e.g., `2function`.
  - **Error**: `SyntaxError`.
  - **Fix**: Start with a letter, e.g., `function2`.

### Why Use Functions?
Functions prevent code repetition, making programs reusable and maintainable.

**Example Code (Without Functions)**:
```python
temp1 = 77
celsius1 = (temp1 - 32) * 5 / 9  # Repeated code
print(celsius1)  # Outputs: 25.0
temp2 = 95
celsius2 = (temp2 - 32) * 5 / 9
print(celsius2)  # Outputs: 35.0
```
**With Functions**:
```python
def fahrenheit_to_celsius(fahrenheit):
    return (fahrenheit - 32) * 5 / 9

print(fahrenheit_to_celsius(77))  # Outputs: 25.0
print(fahrenheit_to_celsius(95))  # Outputs: 35.0
```
- **Explanation**: Function reduces repetition. **Input**: `fahrenheit` (number). **Output**: Celsius value.
- **Common Mistake**: Hardcoding values in functions.
  - **Fix**: Use parameters for flexibility.

### Return Values
Functions use `return` to send data back. Without `return`, they return `None`.

**Example Code**:
```python
def get_greeting():
    return "Hello from a function"  # Outputs: Hello from a function

message = get_greeting()
print(message)
print(get_greeting())  # Direct use
```
- **Explanation**:
  - `return "Hello..."`: Sends string back. **Output**: String.
  - `message = get_greeting()`: Stores returned value.
  - `print(get_greeting())`: Uses return value directly.
- **Common Mistake**: Forgetting `return`, expecting output.
  - **Fix**: Use `return` explicitly.

### The pass Statement
`pass` is a placeholder for empty functions to avoid errors.

**Example Code**:
```python
def my_function():
    pass  # No error, no output
```
- **Explanation**: Prevents `SyntaxError` for empty function.
- **Common Mistake**: Empty function without `pass`.
  - **Error**: `SyntaxError`.
  - **Fix**: Use `pass`.

### Function Arguments
Arguments pass data to functions. Parameters are variables in the function definition; arguments are values passed during calls.

**Example Code**:
```python
def my_function(fname):  # fname is parameter
    print(fname + " Refsnes")  # Outputs: Emil Refsnes, Tobias Refsnes, Linus Refsnes

my_function("Emil")  # Emil is argument
my_function("Tobias")
my_function("Linus")
```
- **Explanation**: `fname` accepts a string. **Output**: Concatenated name.

### Number of Arguments
Functions require the exact number of arguments unless defaults or `*args`/`**kwargs` are used.

**Example Code**:
```python
def my_function(fname, lname):
    print(fname + " " + lname)  # Outputs: Emil Refsnes

my_function("Emil", "Refsnes")
```
- **Common Mistake**: Wrong number of arguments.
  - **Error**: `TypeError`.
  - **Fix**: Match arguments to parameters.

### Default Parameter Values
Parameters can have default values, used if no argument is provided.

**Example Code**:
```python
def my_function(country="Norway"):
    print("I am from", color)  # Outputs: I am from Sweden, India, Norway, Brazil

my_function("Sweden")
my_function("India")
my_function()
my_function("Brazil")
```
- **Explanation**: `color` defaults to `"Norway"`.

### Keyword Arguments
Keyword arguments use `key=value` syntax, ignoring order.

**Example Code**:
```python
def my_function(animal, name):
    print("I have a", animal, "named", name)  # Outputs: I have a dog named Buddy

my_function(animal="dog", name="Buddy")
my_function(name="Buddy", animal="dog")
```
- **Explanation**: Order doesn’t matter with `kwargs`.

### Positional Arguments
Positional arguments rely on order.

**Example Code**:
```python
def my_function(animal, name):
    print("I have a", animal, "named", name)  # Outputs: I have a dog named Buddy

my_function("dog", "Buddy")
my_function("Buddy", "dog")  # Incorrect order
```
- **Common Mistake**: Wrong order changes meaning.
  - **Fix**: Match argument order to parameters.

### Mixing Positional and Keyword Arguments
Positional arguments must precede keyword arguments.

**Example Code**:
```python
def my_function(animal, name, age):
    print("I have a", age, "year old", animal, "named", name)  # Outputs: I have a 5 year old dog named Buddy

my_function("dog", name="Buddy", age=5)
```
- **Common Mistake**: Keyword before positional.
  - **Error**: `SyntaxError`.
  - **Fix**: Positional first.

### Passing Different Data Types
Functions accept any data type (e.g., lists, dictionaries).

**Example Code**:
```python
def my_function(fruits):
    for fruit in fruits:
        print(fruit)  # Outputs: apple, banana, cherry

my_fruits = ["apple", "banana", "cherry"]
my_function(my_fruits)
```
- **Explanation**: `fruits` is a list, iterated inside function.

**Dictionary Example**:
```python
def my_function(person):
    print("Name:", person["name"])  # Outputs: Name: Emil
    print("Age:", person["age"])   # Outputs: Age: 25

my_person = {"name": "Emil", "age": 25}
my_function(my_person)
```

### Returning Different Data Types
Functions can return any data type (e.g., lists, tuples).

**Example Code**:
```python
def my_function():
    return ["apple", "banana", "cherry"]  # Outputs: apple, banana, cherry

fruits = my_function()
for fruit in fruits:
    print(fruit)
```
**Tuple Example**:
```python
def my_function():
    return (10, 20)  # Outputs: x: 10, y: 20

x, y = my_function()
print("x:", x)
print("y:", y)
```

### Positional-Only and Keyword-Only Arguments
Use `, /` for positional-only and `*,` for keyword-only arguments.

**Example Code (Positional-Only)**:
```python
def my_function(name, /):
    print("Hello", name)  # Outputs: Hello Emil

my_function("Emil")
# my_function(name="Emil")  # Error
```
**Keyword-Only**:
```python
def my_function(*, name):
    print("Hello", name)  # Outputs: Hello Emil

my_function(name="Emil")
# my_function("Emil")  # Error
```
**Combined**:
```python
def my_function(a, b, /, *, c, d):
    return a + b + c + d  # Outputs: 50

result = my_function(5, 10, c=15, d=20)
print(result)
```

### Arbitrary Arguments (*args)
`*args` collects positional arguments into a tuple.

**Example Code**:
```python
def my_function(*kids):
    print("The youngest child is", kids[2])  # Outputs: The youngest child is Linus

my_function("Emil", "Tobias", "Linus")
```
- **Explanation**: `kids` is a tuple `(Emil, Tobias, Linus)`.

**With Regular Arguments**:
```python
def my_function(greeting, *names):
    for name in names:
        print(greeting, name)  # Outputs: Hello Emil, Hello Tobias, Hello Linus

my_function("Hello", "Emil", "Tobias", "Linus")
```

### Arbitrary Keyword Arguments (**kwargs)
`**kwargs` collects keyword arguments into a dictionary.

**Example Code**:
```python
def my_function(**kid):
    print("His last name is", kid["lname"])  # Outputs: His last name is Refsnes

my_function(fname="Tobias", lname="Refsnes")
```
**With Regular Arguments**:
```python
def my_function(username, **details):
    print("Username:", username)
    print("Additional details:")
    for key, value in details.items():
        print(" ", key + ":", value)  # Outputs: Username: emil123, age: 25, city: Oslo, hobby: coding

my_function("emil123", age=25, city="Oslo", hobby="coding")
```

### Combining *args and **kwargs
Combine in order: regular parameters, `*args`, `**kwargs`.

**Example Code**:
```python
def my_function(title, *args, **kwargs):
    print("Title:", title)
    print("Positional arguments:", args)
    print("Keyword arguments:", kwargs)  # Outputs: Title: User Info, Positional: (Emil, Tobias), Keyword: {'age': 25, 'city': 'Oslo'}

my_function("User Info", "Emil", "Tobias", age=25, city="Oslo")
```

### Unpacking Arguments
Use `*` to unpack lists and `**` to unpack dictionaries.

**Example Code**:
```python
def my_function(a, b, c):
    return a + b + c  # Outputs: 6

numbers = [1, 2, 3]
print(my_function(*numbers))

person = {"fname": "Emil", "lname": "Refsnes"}
def my_function2(fname, lname):
    print("Hello", fname, lname)  # Outputs: Hello Emil Refsnes

my_function2(**person)
```

### Scope (Local, Global, Nonlocal)
Variables have scope: local (inside function), global (outside), or nonlocal (outer function in nested functions).

**Local Scope**:
```python
def myfunc():
    x = 300  # Local
    print(x)  # Outputs: 300

myfunc()
# print(x)  # Error: x not defined
```

**Function Inside Function**:
```python
def myfunc():
    x = 300
    def myinnerfunc():
        print(x)  # Outputs: 300
    myinnerfunc()

myfunc()
```

**Global Scope**:
```python
x = 300  # Global
def myfunc():
    print(x)  # Outputs: 300

myfunc()
print(x)  # Outputs: 300
```

**Naming Variables (Local vs Global)**:
```python
x = 300  # Global
def myfunc():
    x = 200  # Local
    print(x)  # Outputs: 200

myfunc()
print(x)  # Outputs: 300
```

**Global Keyword**:
```python
def myfunc():
    global x
    x = 200  # Modifies global x

myfunc()
print(x)  # Outputs: 200
```

**Nonlocal Keyword**:
```python
def myfunc1():
    x = "Jane"
    def myfunc2():
        nonlocal x
        x = "hello"
    myfunc2()
    return x  # Outputs: hello

print(myfunc1())
```

### LEGB Rule
Python searches variables in order: Local, Enclosing, Global, Built-in.

**Example Code**:
```python
x = "global"
def outer():
    x = "enclosing"
    def inner():
        x = "local"
        print("Inner:", x)  # Outputs: Inner: local
    inner()
    print("Outer:", x)  # Outputs: Outer: enclosing

outer()
print("Global:", x)  # Outputs: Global: global
```

**One-Line Takeaway**: Python functions, with arguments, return values, and scope rules (LEGB), enable reusable, modular code.

---

## Section 2 — Class Exercise

### Exercise: Temperature Converter

**Objective**: Write a Python program that uses functions to convert temperatures and handle arguments.

**Step-by-Step Instructions**:
1. Create a file named `temp_converter.py`.
2. Define:
   - A function `fahrenheit_to_celsius(fahrenheit)` to convert Fahrenheit to Celsius.
   - A function `print_temps(temps)` to print a list of temperatures in Celsius.
   - A function `describe_temp(*temps)` to print the average of temperatures.
   - A function `log_conversion(**details)` to log conversion details (e.g., `type="F to C", temp=77`).
3. Call each function with appropriate arguments.
4. Add comments to explain each step.
5. Run with `python temp_converter.py`.

**Hints**:
- Use `return` for calculations, not `print`.
- Ensure `*temps` is a tuple and `**details` is a dictionary.
- Use f-strings for clear output.

**Checkpoint**:
- Verify conversions are correct (e.g., 77°F = 25°C).
- Ensure average is calculated correctly.

**Example Output**:
```
Fahrenheit to Celsius:
77°F = 25.0°C
95°F = 35.0°C
List of Temperatures:
25.0°C
35.0°C
10.0°C
Average Temperature:
25.0°C
Conversion Log:
Type: F to C
Original: 77
Converted: 25.0
```

---

## Section 3 — Weekly Project

### Project: Contact Manager

**Objective**: Create a Python program that uses functions to manage a contact list with names and details.

**Milestones**:
1. Create a file named `contact_manager.py`.
2. Define:
   - A function `add_contact(name, /, *, phone, email)` to return a contact dictionary.
   - A function `print_contacts(contacts)` to print all contacts.
   - A function `filter_contacts(*contacts, **criteria)` to filter contacts by criteria (e.g., `phone="123-456-7890"`).
   - A function `update_contact(contact, **updates)` to update contact details.
3. Use a global `contacts` list to store contacts.
4. Validate inputs (e.g., non-empty name, valid phone).
5. Call functions to add, print, filter, and update contacts.
6. Run with `python contact_manager.py`.

**Deliverables**:
- A working `contact_manager.py` file.
- Output showing contact management operations.

**Research Prompts**:
- How does the LEGB rule affect variable access in nested functions?
- Why are functions preferred over repeated code blocks?

**Assessment Criteria**:
- Code runs without errors.
- Functions use correct argument types and return values.
- Validation works.
- Output is clear and commented.
- Scope is handled correctly.

**Extension Idea**:
- Add a function to delete contacts.
- Use a loop to process multiple updates.

**Example Output**:
```
Contact Manager:
Added: {'name': 'Emil', 'phone': '123-456-7890', 'email': 'emil@example.com'}
Added: {'name': 'Tobias', 'phone': '987-654-3210', 'email': 'tobias@example.com'}
All Contacts:
Emil: 123-456-7890, emil@example.com
Tobias: 987-654-3210, tobias@example.com
Filtered Contacts (phone=123-456-7890):
Emil: 123-456-7890, emil@example.com
Updated Contact:
{'name': 'Emil', 'phone': '555-555-5555', 'email': 'emil@example.com'}
All inputs valid
```

---

## Completion Checklist
- [ ] Understood function definition and calling with `def`.
- [ ] Used positional, keyword, default, `*args`, and `**kwargs` arguments.
- [ ] Applied `return` for different data types.
- [ ] Managed local, global, and nonlocal scope with LEGB rule.
- [ ] Used `pass` for placeholders.
- [ ] Completed the class exercise and verified output.
- [ ] Started the weekly project and implemented contact manager.
- [ ] Fixed at least one common mistake (e.g., incorrect argument order).