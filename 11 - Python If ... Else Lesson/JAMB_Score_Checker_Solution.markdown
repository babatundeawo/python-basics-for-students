# **JAMB Score Checker: Python Code Solution and Explanation**

This document provides the complete Python code solution for the **JAMB Score Checker** class exercise, along with a step-by-step explanation. The exercise uses `if`, `elif`, `else`, and logical operators to check a student’s JAMB score and determine their admission status, tailored to a Nigerian context to make it relatable and engaging for beginners.

---

## **Section 1 – Code Solution**

Below is the Python code for the JAMB Score Checker, which prompts the user for their JAMB score, validates it, and prints an appropriate message based on the score range.

```python
# Get JAMB score from user
score = int(input("Enter your JAMB score (0-400): "))

# Check if score is valid (between 0 and 400)
if score >= 0 and score <= 400:
    # Check score ranges for admission status
    if score >= 200:
        print("Great job! You’re eligible for university admission.")
    elif score >= 150:
        print("Good effort! You’re eligible for polytechnic admission.")
    else:
        print("Try again next year.")
else:
    print("Invalid score! JAMB scores are between 0 and 400.")
```

---

## **Section 2 – Explanation**

This section breaks down the code line-by-line, explains the concepts used, and ties them to a Nigerian context to make it relatable for beginners. The explanation follows the lesson’s focus on `if`, `elif`, `else`, and logical operators (`and`), as outlined in the exercise.

### **Code Breakdown**

1. **Line 1: Getting User Input**
   ```python
   score = int(input("Enter your JAMB score (0-400): "))
   ```
   - **What it does**: The `input()` function asks the user to type their JAMB score, displaying the prompt "Enter your JAMB score (0-400): ". The `int()` function converts the input (a string) to an integer so we can perform numerical comparisons.
   - **Why it’s important**: In Nigeria, JAMB scores are numbers (e.g., 250 out of 400), so we need a number, not text, to check conditions.
   - **Relatable Analogy**: This is like a JAMB official asking you for your score on your exam slip. You provide the number, and they check it against the cut-off marks.

2. **Line 3: Validating the Score**
   ```python
   if score >= 0 and score <= 400:
   ```
   - **What it does**: Uses an `if` statement with the `and` logical operator to check two conditions:
     - `score >= 0`: Ensures the score isn’t negative.
     - `score <= 400`: Ensures the score doesn’t exceed JAMB’s maximum of 400.
   - **Why it’s important**: JAMB scores must be between 0 and 400. This check prevents invalid inputs like -10 or 500 from causing incorrect results.
   - **Relatable Analogy**: It’s like a teacher checking if your WAEC score sheet is valid before grading. If the score is impossible (e.g., 500), they reject it.

3. **Line 5: Checking University Admission**
   ```python
   if score >= 200:
       print("Great job! You’re eligible for university admission.")
   ```
   - **What it does**: Inside the valid score block, this `if` checks if `score` is 200 or higher. If true, it prints a message congratulating the user for qualifying for university admission.
   - **Why it’s important**: In Nigeria, a JAMB score of 200 or above is typically required for university admission, making this a realistic threshold.
   - **Relatable Analogy**: This is like getting a JAMB score high enough to apply to the University of Lagos (UNILAG) and feeling proud to share the news with friends.

4. **Line 6: Checking Polytechnic Admission**
   ```python
   elif score >= 150:
       print("Good effort! You’re eligible for polytechnic admission.")
   ```
   - **What it does**: If the score is less than 200 but at least 150, this `elif` prints a message indicating eligibility for polytechnic admission.
   - **Why it’s important**: Polytechnics in Nigeria often have lower cut-off marks (e.g., 150), so this reflects a real-world scenario.
   - **Relatable Analogy**: It’s like qualifying for Yaba College of Technology (YABATECH) with a slightly lower score, still a proud achievement.

5. **Line 8: Handling Scores Below 150**
   ```python
   else:
       print("Try again next year.")
   ```
   - **What it does**: If the score is less than 150 (and valid), this `else` catches all remaining cases and prints a message encouraging the user to try again.
   - **Why it’s important**: Scores below 150 typically don’t qualify for tertiary institutions, mimicking JAMB’s real-world standards.
   - **Relatable Analogy**: It’s like a student who didn’t meet the cut-off being told to prepare harder for the next JAMB exam, a common experience.

6. **Line 10: Handling Invalid Scores**
   ```python
   else:
       print("Invalid score! JAMB scores are between 0 and 400.")
   ```
   - **What it does**: If the first `if` condition (`score >= 0 and score <= 400`) is false, this `else` prints an error message for invalid scores.
   - **Why it’s important**: This ensures the program handles errors gracefully, like rejecting a score of 450 or -10.
   - **Relatable Analogy**: It’s like a JAMB official rejecting a fake score sheet because the numbers don’t make sense.

### **How It Works**
- The program starts by asking for the user’s JAMB score.
- It checks if the score is valid (0 to 400) using `and`.
- If valid, it uses nested `if`, `elif`, and `else` to check score ranges and print the appropriate admission message.
- If invalid, it prints an error message.
- **Example Outputs**:
  - Input: `250` → Output: `Great job! You’re eligible for university admission.`
  - Input: `180` → Output: `Good effort! You’re eligible for polytechnic admission.`
  - Input: `100` → Output: `Try again next year.`
  - Input: `450` → Output: `Invalid score! JAMB scores are between 0 and 400.`

### **Key Concepts Used**
- **Input/Output**: `input()` for user input, `print()` for output.
- **Variables**: `score` stores the user’s input as an integer.
- **Conditions**: `>=` for range checks, `and` for combining conditions.
- **If Statements**: `if`, `elif`, `else` to handle different score ranges.
- **Indentation**: Proper spacing ensures code blocks are correctly grouped.

### **Why It’s Relatable and Fun**
- The JAMB Score Checker mimics a real Nigerian experience: checking if your JAMB score qualifies you for university or polytechnic.
- Students can share this with peers, saying, “I built a program that checks JAMB results like the official website!” It’s practical and boast-worthy.
- It builds confidence by showing how simple Python code can solve a familiar problem, like checking exam results.

---

## **Section 3 – Notes for Beginners**
- **Error Handling**: The code assumes the user enters a number. In a more advanced version, you could add `try/except` to handle non-numeric inputs (e.g., letters).
- **Indentation**: Ensure all lines under `if`, `elif`, and `else` are indented (4 spaces or 1 tab) to avoid errors.
- **Testing**: Try different inputs (e.g., 0, 150, 200, 400, -1, 401) to see how the program responds.
- **Extension Ideas**:
  - Add a prompt to ask if the user is applying for a specific course (e.g., Medicine) and adjust the cut-off (e.g., 250 for Medicine).
  - Include a congratulatory message with the user’s name for scores above 200.

This program is a small but powerful step toward building practical tools, showing how Python can solve real-world Nigerian problems!