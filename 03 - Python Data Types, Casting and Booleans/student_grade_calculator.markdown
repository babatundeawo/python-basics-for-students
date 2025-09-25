# Solution to Student Grade Calculator Project

## Explanation

The **Student Grade Calculator** project requires building a Python program that collects a student’s name (string) and three test scores (floats), stores the scores in a list, calculates the average score, determines if the student passed (average >= 60) using a boolean, and displays a summary. This solution reinforces the concepts of data types (strings, floats, lists, booleans), casting, and input/output from the Python Data Types lesson, while integrating basic calculations and conditionals.

### Step-by-Step Breakdown
1. **Collecting Input**:
   - Use `input()` to get the student’s name (stored as a string).
   - Use `input()` to collect three test scores, casting each to a float to handle decimals (e.g., 85.5).
   - Store the scores in a list to organize them.

2. **Calculating the Average**:
   - Use the `sum()` function to add all scores in the list and divide by `len()` (number of scores) to compute the average.
   - The average is a float, preserving decimal precision.

3. **Determining Pass/Fail**:
   - Use an `if` statement to check if the average is >= 60.
   - Store the result in a boolean variable (`passed`), which will be `True` if the average is 60 or higher, or `False` otherwise.

4. **Displaying the Summary**:
   - Print a message combining the name, average, and pass/fail status, e.g., `"[name]'s average score is [average]. Pass: [True/False]."`
   - Ensure all data types are handled correctly (e.g., converting the average to a string for printing if needed).

5. **Bonus Consideration**:
   - The project suggests allowing a variable number of tests (using loops), but for simplicity, this solution sticks to three tests, as loops are a future topic. Beginners can revisit this later to add the bonus feature.

### Why This Works
- **Data Types**: The program uses strings (name), floats (scores and average), lists (to store scores), and booleans (pass/fail status), aligning with the lesson’s focus.
- **Casting**: Inputs for scores are cast to floats to allow decimal values, reinforcing casting concepts.
- **Lists**: Storing scores in a list introduces beginners to collections, making calculations like `sum()` easier.
- **Booleans**: The pass/fail logic uses a boolean, showing how comparisons (e.g., `average >= 60`) produce `True` or `False`.
- **Real-World Relevance**: This mimics a grading system, making it practical and engaging, while building confidence in combining multiple data types.

### Solution Code
Below is the complete Python code for the Student Grade Calculator, followed by sample output.

```python
# Get student’s name
name = input("Enter the student's name: ")

# Get three test scores and store in a list
score1 = float(input("Enter the first test score: "))
score2 = float(input("Enter the second test score: "))
score3 = float(input("Enter the third test score: "))
scores = [score1, score2, score3]

# Calculate the average score
average = sum(scores) / len(scores)

# Determine if the student passed (average >= 60)
passed = average >= 60

# Print the summary
print(name + "'s average score is", average, ". Pass:", passed)

# Print data types to confirm
print("Data type of name:", type(name))
print("Data type of scores:", type(scores))
print("Data type of average:", type(average))
print("Data type of passed:", type(passed))
```

### Sample Output
If the user enters:
- Name: Amina
- Score 1: 85.5
- Score 2: 90.0
- Score 3: 78.5

The output will be:
```
Enter the student's name: Amina
Enter the first test score: 85.5
Enter the second test score: 90.0
Enter the third test score: 78.5
Amina's average score is 84.66666666666667 . Pass: True
Data type of name: <class 'str'>
Data type of scores: <class 'list'>
Data type of average: <class 'float'>
Data type of passed: <class 'bool'>
```

### Notes for Beginners
- **Error Handling**: This solution assumes valid numeric inputs for scores. In a real program, you might add checks for invalid inputs (e.g., non-numeric values), which you’ll learn about later with error handling.
- **Casting**: The `float()` function ensures scores can include decimals. If you forget to cast, Python treats inputs as strings, causing errors in calculations.
- **Lists**: Using a list to store scores makes it easy to calculate the average and prepares you for more advanced list operations.
- **Precision**: The average may show many decimal places (e.g., 84.66666666666667). You can format it later with string formatting (a future topic).
- **Practice Tip**: Test the program with different scores, including failing ones (e.g., 50, 55, 58), to see how the boolean `passed` changes. Also, use `type()` to explore other variables if curious.

This solution is straightforward, practical, and directly applies the lesson’s concepts of data types, casting, lists, and booleans. It builds confidence by showing how these building blocks create a useful program, while hinting at future topics like loops and formatting.