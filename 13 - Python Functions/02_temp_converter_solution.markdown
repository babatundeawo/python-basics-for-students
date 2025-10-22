# Solution to Python Class Exercise: Temperature Converter

This document provides the solution to the Python class exercise from the Python Functions tutorial, where the task is to create a program that uses functions to convert temperatures and handle arguments. Below is the solution code, followed by a detailed explanation tailored for beginners.

---

## Solution Code

```python
# temp_converter.py
# This program uses functions to convert temperatures and handle arguments

"""
Program: Temperature Converter
Author: [Your Name]
Purpose: Demonstrates using functions with arguments to convert and process temperatures
"""

# Convert Fahrenheit to Celsius
def fahrenheit_to_celsius(fahrenheit):
    return (fahrenheit - 32) * 5 / 9

# Print list of temperatures in Celsius
def print_temps(temps):
    for temp in temps:
        celsius = fahrenheit_to_celsius(temp)
        print(f"{temp}°F = {celsius:.1f}°C")

# Calculate and print average of temperatures
def describe_temp(*temps):
    if not temps:  # Check if temps is empty
        return "No temperatures provided"
    total = sum(temps)
    count = len(temps)
    avg_celsius = fahrenheit_to_celsius(total / count)
    return f"Average Temperature: {avg_celsius:.1f}°C"

# Log conversion details
def log_conversion(**details):
    print("Conversion Log:")
    for key, value in details.items():
        print(f"{key.capitalize()}: {value}")

# Main program
print("Fahrenheit to Celsius:")
temps = [77, 95, 50]
for temp in temps:
    celsius = fahrenheit_to_celsius(temp)
    print(f"{temp}°F = {celsius:.1f}°C")

print("List of Temperatures:")
print_temps(temps)

print("Average Temperature:")
print(describe_temp(77, 95, 50))

print("Conversion Log:")
log_conversion(type="F to C", original=77, converted=fahrenheit_to_celsius(77))
```

**Expected Output**:
```
Fahrenheit to Celsius:
77°F = 25.0°C
95°F = 35.0°C
50°F = 10.0°C
List of Temperatures:
77°F = 25.0°C
95°F = 35.0°C
50°F = 10.0°C
Average Temperature:
25.0°C
Conversion Log:
Type: F to C
Original: 77
Converted: 25.0
```

---

## Explanation

### Objective
The exercise requires creating a Python program (`temp_converter.py`) that:
- Defines a function `fahrenheit_to_celsius(fahrenheit)` to convert Fahrenheit to Celsius.
- Defines a function `print_temps(temps)` to print a list of temperatures in Celsius.
- Defines a function `describe_temp(*temps)` to print the average of temperatures in Celsius.
- Defines a function `log_conversion(**details)` to log conversion details (e.g., `type="F to C", temp=77`).
- Calls each function with appropriate arguments.
- Includes comments to explain each step.
- Runs correctly with `python temp_converter.py`.

### Line-by-Line Breakdown
Let’s walk through the code to understand each part, its input, output, and purpose:

1. **File Creation**:
   - The code is saved in a file named `temp_converter.py`. This ensures Python recognizes it as a Python script when you run `python temp_converter.py`.

2. **Single-Line Comment**:
   ```python
   # temp_converter.py
   # This program uses functions to convert temperatures and handle arguments
   ```
   - **Purpose**: Describes the file and program purpose. Ignored by Python.
   - **Input**: None.
   - **Output**: None.
   - **Side Effects**: None.

3. **Multiline Comment**:
   ```python
   """
   Program: Temperature Converter
   Author: [Your Name]
   Purpose: Demonstrates using functions with arguments to convert and process temperatures
   """
   ```
   - **Purpose**: Provides detailed documentation. Ignored by Python since it’s not assigned.
   - **Input**: None.
   - **Output**: None.
   - **Side Effects**: None.

4. **Function: fahrenheit_to_celsius**:
   ```python
   def fahrenheit_to_celsius(fahrenheit):
       return (fahrenheit - 32) * 5 / 9
   ```
   - **Purpose**: Converts Fahrenheit to Celsius using the formula `(F - 32) * 5/9`.
   - **Input**: `fahrenheit` (number, e.g., 77).
   - **Output**: Celsius value (e.g., 25.0).
   - **Side Effects**: None.
   - **Explanation**: Returns the converted temperature without printing.

5. **Function: print_temps**:
   ```python
   def print_temps(temps):
       for temp in temps:
           celsius = fahrenheit_to_celsius(temp)
           print(f"{temp}°F = {celsius:.1f}°C")
   ```
   - **Purpose**: Prints a list of temperatures in Celsius.
   - **Input**: `temps` (list of numbers, e.g., `[77, 95, 50]`).
   - **Output**: Prints each temperature in Fahrenheit and Celsius (e.g., `77°F = 25.0°C`).
   - **Side Effects**: Prints to terminal.
   - **Explanation**:
     - `for temp in temps`: Iterates over the list.
     - `celsius = fahrenheit_to_celsius(temp)`: Calls conversion function.
     - `print(f"{temp}°F = {celsius:.1f}°C")`: Formats output to one decimal place.

6. **Function: describe_temp**:
   ```python
   def describe_temp(*temps):
       if not temps:
           return "No temperatures provided"
       total = sum(temps)
       count = len(temps)
       avg_celsius = fahrenheit_to_celsius(total / count)
       return f"Average Temperature: {avg_celsius:.1f}°C"
   ```
   - **Purpose**: Calculates and returns the average temperature in Celsius.
   - **Input**: `*temps` (variable number of numbers as a tuple, e.g., `(77, 95, 50)`).
   - **Output**: String with average in Celsius (e.g., `Average Temperature: 25.0°C`).
   - **Side Effects**: None.
   - **Explanation**:
     - `if not temps`: Handles empty input.
     - `total = sum(temps)`: Sums temperatures.
     - `count = len(temps)`: Counts temperatures.
     - `avg_celsius = fahrenheit_to_celsius(total / count)`: Converts average to Celsius.
     - `return f"Average Temperature: {avg_celsius:.1f}°C"`: Formats result.

7. **Function: log_conversion**:
   ```python
   def log_conversion(**details):
       print("Conversion Log:")
       for key, value in details.items():
           print(f"{key.capitalize()}: {value}")
   ```
   - **Purpose**: Logs conversion details from keyword arguments.
   - **Input**: `**details` (dictionary of key-value pairs, e.g., `{"type": "F to C", "original": 77, "converted": 25.0}`).
   - **Output**: Prints each key-value pair (e.g., `Type: F to C`).
   - **Side Effects**: Prints to terminal.
   - **Explanation**:
     - `for key, value in details.items()`: Iterates over dictionary.
     - `print(f"{key.capitalize()}: {value}")`: Capitalizes keys for readability.

8. **Main Program**:
   ```python
   print("Fahrenheit to Celsius:")
   temps = [77, 95, 50]
   for temp in temps:
       celsius = fahrenheit_to_celsius(temp)
       print(f"{temp}°F = {celsius:.1f}°C")

   print("List of Temperatures:")
   print_temps(temps)

   print("Average Temperature:")
   print(describe_temp(77, 95, 50))

   print("Conversion Log:")
   log_conversion(type="F to C", original=77, converted=fahrenheit_to_celsius(77))
   ```
   - **Purpose**: Calls functions to demonstrate functionality.
   - **Explanation**:
     - **First Block**: Converts and prints individual temperatures using `fahrenheit_to_celsius`.
     - **Second Block**: Calls `print_temps` with the `temps` list.
     - **Third Block**: Calls `describe_temp` with individual arguments.
     - **Fourth Block**: Calls `log_conversion` with keyword arguments.
   - **Output**: Matches expected output with formatted temperatures and log.

### Visual Description
When you run `python temp_converter.py` in the terminal, the output is:
```
Fahrenheit to Celsius:
77°F = 25.0°C
95°F = 35.0°C
50°F = 10.0°C
List of Temperatures:
77°F = 25.0°C
95°F = 35.0°C
50°F = 10.0°C
Average Temperature:
25.0°C
Conversion Log:
Type: F to C
Original: 77
Converted: 25.0
```
Each section is clearly labeled, showing conversions, list processing, average, and log details, all formatted to one decimal place for Celsius values.

### Common Mistakes and Fixes
1. **Printing Instead of Returning**:
   - **Mistake**:
     ```python
     def fahrenheit_to_celsius(fahrenheit):
         print((fahrenheit - 32) * 5 / 9)  # Prints instead of returns
     ```
   - **Error**: Function returns `None`, causing issues in `print_temps` or `describe_temp`.
   - **Fix**: Use `return`:
     ```python
     def fahrenheit_to_celsius(fahrenheit):
         return (fahrenheit - 32) * 5 / 9
     ```
2. **Not Handling Empty `*temps`**:
   - **Mistake**:
     ```python
     def describe_temp(*temps):
         total = sum(temps)
         count = len(temps)
         avg_celsius = fahrenheit_to_celsius(total / count)
         return f"Average Temperature: {avg_celsius:.1f}°C"
     ```
   - **Error**: `ZeroDivisionError` if `temps` is empty.
   - **Fix**: Add check:
     ```python
     if not temps:
         return "No temperatures provided"
     ```
3. **Incorrect Argument Type**:
   - **Mistake**:
     ```python
     print_temps(77)  # Single number instead of list
     ```
   - **Error**: `TypeError` (int is not iterable).
   - **Fix**: Pass a list:
     ```python
     print_temps([77])
     ```
4. **Forgetting `.items()` in `**kwargs`**:
   - **Mistake**:
     ```python
     def log_conversion(**details):
         for key, value in details:  # Missing .items()
             print(f"{key.capitalize()}: {value}")
     ```
   - **Error**: `TypeError` (dictionary not iterable).
   - **Fix**: Use `details.items()`:
     ```python
     for key, value in details.items():
     ```
5. **Wrong File Extension**:
   - **Mistake**: Saving as `temp_converter.txt`.
   - **Fix**: Save as `temp_converter.py` and run with `python temp_converter.py`.

### Validation Check
To confirm the program works:
1. Save the code in `temp_converter.py`.
2. Open a terminal, navigate to the file’s directory, and run `python temp_converter.py`.
3. Verify the output matches: `77°F = 25.0°C`, `95°F = 35.0°C`, `50°F = 10.0°C`, average `25.0°C`, and correct log details.
4. Test with different inputs (e.g., `temps = [32]` should output `32°F = 0.0°C`).
5. Add `print(type(temps))` in `print_temps` to confirm `temps` is a list (`<class 'list'>`).
6. Test `describe_temp()` with no arguments to confirm it returns `"No temperatures provided"`.

### One-Line Takeaway
This program demonstrates functions with positional arguments, `*args`, and `**kwargs` to convert, print, and analyze temperatures, emphasizing reusable code.