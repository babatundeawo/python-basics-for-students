# Python Numbers for Beginners

This tutorial covers Python’s numeric data types (`int`, `float`, `complex`), type conversion, and generating random numbers using the `random` module. Below is a beginner-friendly teaching package designed to guide learners toward intermediate-level mastery with practical examples and exercises.

---

## Section 1 — Topical Explanations

### Learning Goals
- Understand Python’s three numeric types: `int`, `float`, and `complex`.
- Learn how to check numeric types using `type()`.
- Master type conversion between `int`, `float`, and `complex` using constructor functions.
- Explore generating random numbers with the `random` module.
- Apply numeric types in practical scenarios with proper validation.

### Numeric Types
Python has three built-in numeric types:
- **int**: Whole numbers (positive or negative) without decimals, e.g., `1`, `-3255522`.
- **float**: Numbers with decimals or in scientific notation, e.g., `2.8`, `35e3` (35000.0).
- **complex**: Numbers with a real and imaginary part, written with `j`, e.g., `3+5j`.

Think of numeric types like different tools in a toolbox: `int` for exact counts, `float` for measurements with fractions, and `complex` for advanced math with imaginary numbers.

**Example Code**:
```python
x = 1  # Integer
y = 2.8  # Float
z = 1j  # Complex
print(type(x))  # Outputs: <class 'int'>
print(type(y))  # Outputs: <class 'float'>
print(type(z))  # Outputs: <class 'complex'>
```
- **Line-by-Line Explanation**:
  - `x = 1`: Assigns integer `1` to `x`. **Input**: `1`. **Output**: None. **Side Effects**: `x` holds `1`.
  - `y = 2.8`: Assigns float `2.8` to `y`. **Input**: `2.8`. **Output**: None. **Side Effects**: `y` holds `2.8`.
  - `z = 1j`: Assigns complex number `1j` to `z`. **Input**: `1j`. **Output**: None. **Side Effects**: `z` holds `1j`.
  - `print(type(x))`: Displays `<class 'int'>`. **Input**: `x`. **Output**: `<class 'int'>`.
  - Similarly for `y` and `z`.
- **Visual Description**: Running this code shows `<class 'int'>`, `<class 'float'>`, `<class 'complex'>` on separate lines in the terminal.
- **Common Mistake**: Forgetting parentheses in `type()`.
  - **Error**: `NameError: name 'type' is not defined`.
  - **Fix**: Use `type(x)`, not `type x`.
- **Validation Check**: After assigning each variable, use `print(type(var))` to confirm the correct type.

### Integers (`int`)
Integers are whole numbers (positive, negative, or zero) without decimals, with unlimited length.

**Example Code**:
```python
x = 1  # Small integer
y = 35656222554887711  # Large integer
z = -3255522  # Negative integer
print(x, type(x))  # Outputs: 1 <class 'int'>
print(y, type(y))  # Outputs: 35656222554887711 <class 'int'>
print(z, type(z))  # Outputs: -3255522 <class 'int'>
```
- **Explanation**:
  - Each variable (`x`, `y`, `z`) is an integer, regardless of size or sign.
  - Python handles large integers without special syntax.
- **Common Mistake**: Assuming a large number requires a different type.
  - **Fix**: Python’s `int` type supports unlimited length.

### Floats (`float`)
Floats are numbers with decimals or in scientific notation (using `e` for powers of 10).

**Example Code**:
```python
x = 1.10  # Decimal
y = 1.0  # Decimal (still a float)
z = -35.59  # Negative decimal
w = 35e3  # Scientific notation: 35 * 10^3 = 35000.0
print(x, type(x))  # Outputs: 1.10 <class 'float'>
print(y, type(y))  # Outputs: 1.0 <class 'float'>
print(z, type(z))  # Outputs: -35.59 <class 'float'>
print(w, type(w))  # Outputs: 35000.0 <class 'float'>
```
- **Explanation**:
  - `x`, `y`, `z`: Floats with decimal points.
  - `w`: Scientific notation `35e3` means `35 * 10^3`, resulting in `35000.0`.
- **Common Mistake**: Writing `e` notation incorrectly, e.g., `35e-3.5`.
  - **Error**: `SyntaxError` or incorrect value.
  - **Fix**: Use integer exponents, e.g., `35e3` or `35e-3`.
- **Validation Check**: Print the value and type to confirm scientific notation converts correctly.

### Complex Numbers (`complex`)
Complex numbers have a real part and an imaginary part (with `j`).

**Example Code**:
```python
x = 3+5j  # Real (3) + imaginary (5j)
y = 5j  # Pure imaginary
z = -5j  # Negative imaginary
print(x, type(x))  # Outputs: (3+5j) <class 'complex'>
print(y, type(y))  # Outputs: 5j <class 'complex'>
print(z, type(z))  # Outputs: (-0-5j) <class 'complex'>
```
- **Explanation**:
  - `x`: Combines real (`3`) and imaginary (`5j`) parts.
  - `y`, `z`: Pure imaginary numbers (real part is `0`).
- **Common Mistake**: Using `i` instead of `j`.
  - **Error**: `NameError: name 'i' is not defined`.
  - **Fix**: Use `j` for the imaginary unit, e.g., `5j`.

### Type Conversion
You can convert between numeric types using `int()`, `float()`, and `complex()`, but complex numbers cannot be converted to `int` or `float`.

**Example Code**:
```python
x = 1  # int
y = 2.8  # float
z = 1j  # complex
a = float(x)  # Convert int to float
b = int(y)  # Convert float to int (truncates)
c = complex(x)  # Convert int to complex
print(a, type(a))  # Outputs: 1.0 <class 'float'>
print(b, type(b))  # Outputs: 2 <class 'int'>
print(c, type(c))  # Outputs: (1+0j) <class 'complex'>
```
- **Line-by-Line Explanation**:
  - `a = float(x)`: Converts `1` to `1.0`. **Input**: `1`. **Output**: None. **Side Effects**: `a` holds `1.0`.
  - `b = int(y)`: Converts `2.8` to `2` (truncates decimals). **Input**: `2.8`. **Output**: None. **Side Effects**: `b` holds `2`.
  - `c = complex(x)`: Converts `1` to `(1+0j)`. **Input**: `1`. **Output**: None. **Side Effects**: `c` holds `(1+0j)`.
- **Common Mistake**: Trying to convert a complex number to `int` or `float`.
  - **Error**: `TypeError: can't convert complex to int`.
  - **Fix**: Avoid converting complex numbers to non-complex types.
- **Validation Check**: Print the type and value after conversion to confirm the result.

### Random Numbers
Python’s `random` module generates random numbers, such as with `random.randrange(start, stop)` for integers in a range.

**Example Code**:
```python
import random  # Import random module
print(random.randrange(1, 10))  # Outputs: Random integer from 1 to 9
```
- **Explanation**:
  - `import random`: Loads the `random` module.
  - `random.randrange(1, 10)`: Generates a random integer from `1` to `9` (excludes `10`). **Output**: Varies, e.g., `7`.
- **Common Mistake**: Forgetting to import `random`.
  - **Error**: `NameError: name 'random' is not defined`.
  - **Fix**: Add `import random` at the start.
- **Validation Check**: Run multiple times to confirm different numbers are generated.

**One-Line Takeaway**: Python’s numeric types (`int`, `float`, `complex`) handle numbers, with type conversion for flexibility and the `random` module for generating random integers.

---

## Section 2 — Class Exercise

### Exercise: Numeric Type Tester

**Objective**: Write a Python program that explores numeric types, type conversion, and random number generation.

**Step-by-Step Instructions**:
1. Create a file named `numbers.py`.
2. Declare variables:
   - `whole_num` (integer, e.g., `15`).
   - `decimal_num` (cast string `"3.14"` to float).
   - `complex_num` (complex, e.g., `2+3j`).
   - `random_num` (random integer from 1 to 100 using `random.randrange()`).
3. Print each variable’s value and type using `type()`.
4. Convert `whole_num` to float and `decimal_num` to integer, then print the results and their types.
5. Add comments to explain each variable.
6. Run the program with `python numbers.py`.

**Hints**:
- Use `float(whole_num)` for conversion.
- Import `random` for `random_num`.
- Use commas in `print()` to combine values and types.

**Checkpoint**:
- Check if the output shows correct values and types.
- Run multiple times to verify `random_num` changes.

**Example Output** (example for `whole_num = 15`, `decimal_num = "3.14"`, `complex_num = 2+3j`, `random_num` varies):
```
Whole Number: 15 , Type: <class 'int'>
Decimal Number: 3.14 , Type: <class 'float'>
Complex Number: (2+3j) , Type: <class 'complex'>
Random Number: 42 , Type: <class 'int'>
Converted Whole to Float: 15.0 , Type: <class 'float'>
Converted Decimal to Int: 3 , Type: <class 'int'>
```

---

## Section 3 — Weekly Project

### Project: Numeric Profile Calculator

**Objective**: Create a Python program that calculates and validates numeric data for a user profile, incorporating type conversion and random numbers.

**Milestones**:
1. Create a file named `numeric_profile.py`.
2. Declare variables:
   - `age` (integer, cast from string `"30"`).
   - `height` (float, cast from integer `175`).
   - `weight` (float, e.g., `70.5`).
   - `lucky_number` (random integer from 1 to 50 using `random.randrange()`).
3. Calculate `bmi` (float, using formula: `weight / (height/100 * height/100)`).
4. Print each variable’s value and type using `type()`.
5. Convert `age` to float and `bmi` to integer, then print results and types.
6. Use `isinstance()` to validate that `age` is an integer and `height` is a float.
7. Add comments to explain each section.

**Deliverables**:
- A working `numeric_profile.py` file.
- Output showing variable values, types, converted values, and validation results.

**Research Prompts**:
- Why can’t complex numbers be converted to `int` or `float`?
- How does `random.randrange()` differ from `random.randint()`?

**Assessment Criteria**:
- Code runs without errors.
- Variables are correctly typed using constructors.
- BMI calculation is accurate.
- Output includes values, types, and validation results.
- Comments explain key steps.

**Extension Idea**:
- Add a boolean variable `is_healthy` (check if `bmi` is between 18.5 and 24.9).
- Use a function to generate a random `lucky_number` and return it.

**Example Output** (example for `age = "30"`, `height = 175`, `weight = 70.5`, `lucky_number` varies):
```
Age: 30 , Type: <class 'int'>
Height: 175.0 , Type: <class 'float'>
Weight: 70.5 , Type: <class 'float'>
Lucky Number: 42 , Type: <class 'int'>
BMI: 23.02 , Type: <class 'float'>
Converted Age to Float: 30.0 , Type: <class 'float'>
Converted BMI to Int: 23 , Type: <class 'int'>
Is age an integer? True
Is height a float? True
```

---

## Completion Checklist
- [ ] Understood Python’s numeric types (`int`, `float`, `complex`).
- [ ] Used `type()` to check variable types.
- [ ] Performed type conversion with `int()`, `float()`, and `complex()`.
- [ ] Generated random numbers using `random.randrange()`.
- [ ] Completed the class exercise and verified the output.
- [ ] Started the weekly project and planned the numeric profile calculator.
- [ ] Fixed at least one common mistake (e.g., invalid casting or missing import).