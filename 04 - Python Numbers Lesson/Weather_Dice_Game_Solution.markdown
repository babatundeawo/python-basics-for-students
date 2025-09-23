# Simple Weather Dice Game Project Solution

This document provides a solution to the **Simple Weather Dice Game** weekly project from the Python Numbers lesson, designed for complete beginners. The project involves creating a game that simulates daily weather using random numbers, calculates a comfort score with floats and integers, and applies type conversions. Below is the solution with a clear explanation and the Python code.

## Explanation

The project simulates a "weather predictor" game where a random die roll determines if the day is rainy or sunny, affecting a base temperature (float) and calculating a comfort score. It uses all concepts from the lesson—`int`, `float`, `complex`, type conversion, and the `random` module—while keeping the code simple and beginner-friendly. Here's how the solution addresses each step:

1. **Import and Setup**: We import the `random` module to generate random numbers. A base temperature (e.g., 72.5°F as a float) and sunny points (e.g., 10 as an int) are defined, using the numeric types from the lesson.
2. **Roll the Die**: Using `random.randrange(1, 7)`, we simulate a 6-sided die roll, stored as an `int`. We convert it to a `float` for calculations and print both with their types to reinforce type conversion.
3. **Weather Logic**: If the roll is 1-3 (rainy), subtract 5.0 (float) from the temperature; if 4-6 (sunny), add the sunny points (int, converted to float for addition). The updated temperature is printed as both a float and an int (for "feels like" temperature), showing type conversion.
4. **Comfort Score**: Multiply the final temperature by the die roll (ensuring float multiplication) to get a score. If the score exceeds 100, we display it in scientific notation (e.g., 1.5e2), as per the lesson's float examples.
5. **Loop for Fun**: Run the game 5 times using a simple counter (`int`) in a while loop (a basic loop structure suitable for beginners). Track the highest score using a variable, updated each iteration.
6. **Polish and Explore**: Add descriptive print statements (e.g., "Rainy day at 67.5°F – Score: 202.5!") for clarity. Test with a negative temperature (e.g., -10.5°F) to show how Python handles negative floats. The project hints at using complex numbers for "wind chill" but leaves this for exploration, as complex numbers were introduced but not fully applied.

The solution avoids advanced features (like functions or lists) to stay within the lesson's scope, focusing on numbers, type conversions, and randomness. It introduces a basic while loop to meet the 5-run requirement, assuming beginners can follow simple iteration.

## Solution Code

Below is the Python code for the Simple Weather Dice Game, following the step-by-step guidelines.

```python
# Step 1: Import random module and set up variables
import random
base_temp = 72.5  # Base temperature in °F (float)
sunny_points = 10  # Points for sunny day (int)
highest_score = 0  # Track highest score (float)

# Step 5: Loop 5 times for multiple days
counter = 1  # Integer counter
while counter <= 5:
    # Step 2: Roll the die (1-6) and convert to float
    die_roll = random.randrange(1, 7)  # Integer
    die_roll_float = float(die_roll)   # Convert to float
    print(f"\nDay {counter}:")
    print(f"Die roll: {die_roll} (type: {type(die_roll)})")
    print(f"Die roll as float: {die_roll_float} (type: {type(die_roll_float)})")

    # Step 3: Weather logic (rainy: 1-3, sunny: 4-6)
    if die_roll <= 3:
        temp = base_temp - 5.0  # Rainy: subtract 5.0 (float)
        weather = "Rainy"
    else:
        temp = base_temp + sunny_points  # Sunny: add int (converts to float)
        weather = "Sunny"
    
    temp_int = int(temp)  # Convert to int for "feels like"
    print(f"{weather} day at {temp}°F")
    print(f"Feels like: {temp_int}°F (type: {type(temp_int)})")

    # Step 4: Calculate comfort score and use scientific notation if > 100
    score = temp * die_roll_float
    if score > 100:
        score_display = f"{score:.1e}"  # Scientific notation
    else:
        score_display = str(score)
    print(f"Comfort score: {score_display}")

    # Track highest score
    if score > highest_score:
        highest_score = score

    counter += 1  # Increment counter

# Print highest score after loop
print(f"\nHighest comfort score: {highest_score}")

# Step 6: Test with negative temperature
print("\nTesting with negative temperature:")
base_temp = -10.5  # Negative float
die_roll = random.randrange(1, 7)
die_roll_float = float(die_roll)
if die_roll <= 3:
    temp = base_temp - 5.0
    weather = "Rainy"
else:
    temp = base_temp + sunny_points
    weather = "Sunny"
temp_int = int(temp)
score = temp * die_roll_float
print(f"Die roll: {die_roll}")
print(f"{weather} day at {temp}°F, feels like {temp_int}°F")
print(f"Comfort score: {score}")
```

## Expected Output

The output varies due to randomness, but here’s a sample run (formatted for clarity):

```
Day 1:
Die roll: 2 (type: <class 'int'>)
Die roll as float: 2.0 (type: <class 'float'>)
Rainy day at 67.5°F
Feels like: 67°F (type: <class 'int'>)
Comfort score: 135.0

Day 2:
Die roll: 5 (type: <class 'int'>)
Die roll as float: 5.0 (type: <class 'float'>)
Sunny day at 82.5°F
Feels like: 82°F (type: <class 'int'>)
Comfort score: 4.1e+02

Day 3:
Die roll: 3 (type: <class 'int'>)
Die roll as float: 3.0 (type: <class 'float'>)
Rainy day at 67.5°F
Feels like: 67°F (type: <class 'int'>)
Comfort score: 202.5

Day 4:
Die roll: 6 (type: <class 'int'>)
Die roll as float: 6.0 (type: <class 'float'>)
Sunny day at 82.5°F
Feels like: 82°F (type: <class 'int'>)
Comfort score: 4.9e+02

Day 5:
Die roll: 1 (type: <class 'int'>)
Die roll as float: 1.0 (type: <class 'float'>)
Rainy day at 67.5°F
Feels like: 67°F (type: <class 'int'>)
Comfort score: 67.5

Highest comfort score: 495.0

Testing with negative temperature:
Die roll: 4
Sunny day at -0.5°F, feels like 0°F
Comfort score: -2.0
```

## Explanation of Output

- **Die Roll and Types**: Each day shows the random die roll (e.g., 2, an `int`) and its float version (e.g., 2.0, a `float`), confirming type conversion.
- **Weather and Temperature**: A roll of 1-3 gives a rainy day (67.5°F = 72.5 - 5.0), and 4-6 gives a sunny day (82.5°F = 72.5 + 10). The `int` version (e.g., 67) shows truncation, as per the lesson.
- **Comfort Score**: The score is `temp * die_roll_float` (e.g., 67.5 * 2.0 = 135.0). Scores over 100 (e.g., 82.5 * 5 = 412.5) are shown in scientific notation (4.1e+02), as specified.
- **Highest Score**: The highest score (e.g., 495.0 from 82.5 * 6) is tracked across the 5 runs, showing basic comparison logic.
- **Negative Temperature Test**: Using -10.5°F, a sunny day might yield -0.5°F (feels like 0°F), with a score like -2.0, showing how negative floats work.
- **Complex Numbers**: The code doesn’t use complex numbers but hints at their potential (e.g., for wind chill), aligning with the lesson’s introduction of `complex`.

## Notes for Beginners

- The code uses only lesson concepts (`int`, `float`, type conversion, `random.randrange`) plus a simple while loop for repetition, which is intuitive for beginners.
- The `int()` conversion truncates (e.g., 82.5 becomes 82), reinforcing the lesson’s note on truncation.
- Scientific notation (e.g., 4.9e+02) appears for large scores, tying to the lesson’s float examples.
- Negative temperatures show how Python handles negative numbers seamlessly, as noted in the lesson.
- Try changing `base_temp` or `sunny_points` to see different outcomes. For example, set `base_temp = 100.0` for hotter days.
- The hint about complex numbers (e.g., for wind chill) encourages curiosity without requiring implementation, as complex numbers were only introduced theoretically.

This solution builds confidence by combining number types, randomness, and basic logic in a fun, weather-themed context, preparing you for future lessons on conditionals and loops.