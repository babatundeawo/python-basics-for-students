# Python Numbers Lesson

## Section 1 – Explanations

Python handles numbers through three main types: `int` (integers), `float` (floating-point numbers), and `complex` (complex numbers). These types are automatically created when you assign a numeric value to a variable, and you can check a variable's type using the `type()` function.

### Integers (`int`)
An `int` is a whole number (positive, negative, or zero) with no decimal places. Python supports integers of any length, making them flexible for large values.

**Example:**
```python
x = 1
y = 35656222554887711
z = -3255522

print(type(x))
print(type(y))
print(type(z))
```
This outputs `<class 'int'>` for each, confirming they are all integers.

### Floats (`float`)
A `float` is a number with decimal places (positive, negative, or zero). It can also be expressed in scientific notation using "e" or "E" to represent powers of 10 (e.g., 35e3 means 35 × 10³ = 35,000).

**Example (basic floats):**
```python
x = 1.10
y = 1.0
z = -35.59

print(type(x))
print(type(y))
print(type(z))
```
This outputs `<class 'float'>` for each.

**Example (scientific notation):**
```python
x = 35e3
y = 12E4
z = -87.7e100

print(type(x))
print(type(y))
print(type(z))
```
Again, this outputs `<class 'float'>` for each, showing how "e" creates large or precise floats.

### Complex Numbers (`complex`)
A `complex` number includes a real part and an imaginary part (marked by "j"). The real part is optional if it's zero.

**Example:**
```python
x = 3+5j
y = 5j
z = -5j

print(type(x))
print(type(y))
print(type(z))
```
This outputs `<class 'complex'>` for each.

### Type Conversion
You can convert between numeric types using built-in functions like `int()`, `float()`, and `complex()`. However, you cannot convert a `complex` number to `int` or `float`.

**Example:**
```python
x = 1    # int
y = 2.8  # float
z = 1j   # complex

# Convert from int to float:
a = float(x)

# Convert from float to int:
b = int(y)

# Convert from int to complex:
c = complex(x)

print(a)
print(b)
print(c)

print(type(a))
print(type(b))
print(type(c))
```
This outputs:
```
1.0
2
(1+0j)
<class 'float'>
<class 'int'>
<class 'complex'>
```
Note how `int(2.8)` truncates the decimal to 2 (no rounding).

### Random Numbers
Python's `random` module generates random numbers. Import it first, then use functions like `randrange()` to pick a random integer in a range.

**Example:**
```python
import random

print(random.randrange(1, 10))
```
This prints a random integer between 1 and 9 (inclusive of 1, exclusive of 10). Each run may give a different result, like 7 or 3.

These concepts build a foundation for working with numbers in Python, starting from simple assignments and types, then conversions, and finally randomness for variety.

## Section 2 – Class Exercise

**Real-World Problem: Grocery Total Calculator**  
Imagine you're helping a friend shop for groceries. You need to calculate the total cost of items, where prices are decimals (floats), quantities are whole numbers (ints), and you might need to convert types for simple math. This connects to basic variable assignment from earlier lessons.

**Step-by-Step Guidance:**  
1. Create variables: Assign an `int` for the quantity of apples (e.g., 3) and a `float` for the price per apple (e.g., 1.5).  
2. Calculate the subtotal: Multiply quantity by price (result will be a `float`). Print the subtotal and its type using `type()`.  
3. Add tax: Assign a `float` for tax rate (e.g., 0.08 for 8%). Multiply subtotal by tax rate to get tax amount, then add it to subtotal for total. Print the total.  
4. Convert for display: Use `int()` to convert the total to a whole number (truncating decimals) and print both versions to show the difference.  
5. Test variations: Change the quantity to a large `int` (like 1000) and run again to see how Python handles big numbers.  

Run your code multiple times to verify outputs. What happens if you try converting a negative price? Experiment safely!

## Section 3 – Weekly Project

**Project Brief: Simple Weather Dice Game**  
Build a fun "weather predictor" game where a virtual die roll (using random numbers) simulates daily weather, and you calculate a "comfort score" based on temperature (floats) and conditions (ints for sunny/rainy days). This combines all lesson concepts—types, conversions, and randomness—while sparking curiosity about real weather data (hint: next lessons might explore user input for custom forecasts).

**Why This Project?**  
It's a playful way to practice numbers in a scenario like checking the weather app, encouraging you to think about how computers model uncertainty (randomness) and precision (floats vs. ints). Aim for 20-50 lines of code to keep it manageable.

**Step-by-Step Guidelines to Get Started and Stay on Track:**  
1. **Import and Setup:** Start by importing the `random` module. Create a `float` variable for base temperature (e.g., 72.5°F) and an `int` for "sunny points" (e.g., 10).  
2. **Roll the Die:** Use `random.randrange(1, 7)` to simulate a die roll (1-6). Assign this to an `int` variable. Convert it to `float` for calculations and print both with their types.  
3. **Weather Logic:** If the roll is 1-3 (rainy), subtract 5.0 from the temperature (use float conversion). If 4-6 (sunny), add the sunny points. Print the updated temperature as both `float` and converted `int` (for "feels like" whole degrees).  
4. **Comfort Score:** Multiply the final temperature by the die roll (convert types as needed) to get a score. Use scientific notation for a very hot day (e.g., if score > 100, print as 1.5e2).  
5. **Loop for Fun:** Run the game 5 times in a loop (use a simple counter `int`). Track the highest score in a variable.  
6. **Polish and Explore:** Add print statements like "Rainy day at 67.2°F – Score: 402!" Test with negative temps (e.g., -10.5 for winter). To spark curiosity, think: How could you add complex numbers for "wind chill" math? (Save that idea for later!)  

Test incrementally—start with one roll, then add scoring. Share your code with a friend and compare "weather days." What random roll gives the wildest score? This builds confidence in mixing types creatively.