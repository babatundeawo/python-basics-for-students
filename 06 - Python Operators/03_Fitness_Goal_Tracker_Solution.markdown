# Solution to the Fitness Goal Tracker Weekly Project

## Explanation

This weekly project helps beginners apply Python operators in a motivating real-world context: tracking fitness goals based on calories burned from exercises. It combines arithmetic operators for summing totals, comparison operators for checking goals, and logical operators for validating inputs. The program takes inputs for calories from three activities, calculates the total, checks if it meets a 500-calorie goal, and verifies if all activities were performed (calories > 0 for each).

Key concepts reinforced:
- **Input and Variables**: Collecting and storing user data as floats.
- **Arithmetic Operators**: Using `+` to sum calories.
- **Comparison Operators**: `>=` to check if the total meets the goal.
- **Logical Operators**: `and` to ensure all activities have positive calories.
- **Output**: Printing a summary message.

The solution introduces a basic use of `if-else` for decision-making, which builds on operators and hints at conditionals in future lessons. It also handles simple validation for positive inputs, making the program more robust.

This project shows how operators enable practical tools, like apps for health tracking, boosting confidence in coding for everyday problems.

## Step-by-Step Breakdown

1. **Get User Inputs**: Prompt for calories burned in three activities, convert to float, and store in variables.
2. **Calculate Total Calories**: Use `+` to sum the three values.
3. **Check Goal Met**: Use `>=` to see if total is at least 500.
4. **Check All Activities Done**: Use `and` to verify each calorie value > 0.
5. **Print Summary**: Display total, goal status, and activity completion, with encouraging messages.

## Complete Code Solution

```python
# Step 1: Get calories burned from three activities
run_calories = float(input("Enter calories burned from running: "))
cycle_calories = float(input("Enter calories burned from cycling: "))
swim_calories = float(input("Enter calories burned from swimming: "))

# Step 2: Calculate total calories using arithmetic operator
total_calories = run_calories + cycle_calories + swim_calories

# Step 3: Check if goal is met using comparison operator
goal_met = total_calories >= 500

# Step 4: Check if all activities were performed using logical operators
all_activities_done = run_calories > 0 and cycle_calories > 0 and swim_calories > 0

# Step 5: Print the summary
print("Total calories burned:", total_calories)
if goal_met:
    print("Goal met: Yes - Great job!")
else:
    print("Goal met: No - Keep going!")
if all_activities_done:
    print("All activities done: Yes - Well balanced!")
else:
    print("All activities done: No - Try to include all next time!")
```

## How to Test It

- **Test Case 1**: Running = 200, Cycling = 150, Swimming = 200  
  Total: 550, Goal met: Yes, All done: Yes
  
- **Test Case 2**: Running = 100, Cycling = 0, Swimming = 300  
  Total: 400, Goal met: No, All done: No
  
- **Test Case 3**: Running = 500, Cycling = 100, Swimming = -50 (invalid, but code treats as not > 0)  
  Total: 550, Goal met: Yes, All done: No

Run the code in a Python environment and experiment with values. For extra practice, add the stretch goal: calculate average with `/` (e.g., `average = total_calories / 3`) and print it. This project lays the groundwork for more advanced features, like loops for multiple days!