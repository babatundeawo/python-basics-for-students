# **Solution to the “JAMB Score Checker” Project**

This markdown file provides the complete Python code solution for the **JAMB Score Checker** project from the lesson on **while loops** and **for loops**, along with a detailed explanation. The project is designed to reinforce loop concepts, variables, and input/output using a Nigerian-themed scenario that is practical and boast-worthy for beginners.

---

## **Section 1 – Code Solution**

Below is the Python code that implements the “JAMB Score Checker” project. The program uses a **for loop** to collect JAMB scores for a list of subjects, skips invalid scores, stops early if the Physics score is below 50, and uses a **while loop** to count valid scores. It also calculates the total score and provides feedback.

```python
# JAMB Score Checker

# Initialize variables
subjects = ["English", "Maths", "Physics", "Chemistry"]
total_score = 0
valid_scores_count = 0

# Part 1: For loop to collect scores
print("Enter your JAMB scores for each subject (0-100):")
for subject in subjects:
    score = input(f"Score for {subject}: ")
    # Convert input to integer, handle invalid inputs
    try:
        score = int(score)
        if score < 0 or score > 100:
            print(f"Invalid score for {subject}! Must be between 0 and 100. Skipping...")
            continue
        # Check for Physics score below 50
        if subject == "Physics" and score < 50:
            print(f"Physics score {score} is below 50! Stopping score entry.")
            break
        total_score += score
        valid_scores_count += 1
    except ValueError:
        print(f"Invalid input for {subject}! Please enter a number. Skipping...")
        continue

# Part 2: While loop to confirm valid scores count
print("\nConfirming valid scores entered:")
count = 1
while count <= valid_scores_count:
    print(f"Valid score {count} recorded")
    count += 1
else:
    print("All scores checked!")

# Part 3: Display total score and feedback
print(f"\nTotal score: {total_score}")
if total_score > 250 and valid_scores_count == 4:
    print("Congratulations! Your score is above 250, great for many courses!")
elif valid_scores_count < 4:
    print("Not all subjects were scored. Try again to enter all scores.")
```

**Sample Output** (Example Run):
```
Enter your JAMB scores for each subject (0-100):
Score for English: 85
Score for Maths: 90
Score for Physics: 45
Physics score 45 is below 50! Stopping score entry.

Confirming valid scores entered:
Valid score 1 recorded
Valid score 2 recorded
All scores checked!

Total score: 175
Not all subjects were scored. Try again to enter all scores.
```

---

## **Section 2 – Explanation**

This section explains the code step-by-step, connecting it to Nigerian experiences and ensuring clarity for beginners. The explanation follows the **AI Instructional Framework for Teaching Python Beginners (Nigeria-Focused Edition)**, focusing on the concepts used in the project: **for loops**, **while loops**, **continue**, **break**, **else**, **variables**, **input/output**, and **conditionals**.

### **Line-by-Line Breakdown**

#### **Initialization**
```python
subjects = ["English", "Maths", "Physics", "Chemistry"]
total_score = 0
valid_scores_count = 0
```
- **Purpose**: 
  - `subjects`: A list of JAMB subjects, like the ones on a JAMB result slip.
  - `total_score`: Tracks the sum of valid scores, starting at 0.
  - `valid_scores_count`: Counts how many valid scores are entered, starting at 0.
- **Relatable Example**: This is like preparing a JAMB result sheet where you’ll record scores for each subject, similar to how a teacher marks a report card.

#### **Part 1: For Loop to Collect Scores**
```python
print("Enter your JAMB scores for each subject (0-100):")
for subject in subjects:
    score = input(f"Score for {subject}: ")
```
- **Line 1: `print(...)`** – Prints a header to guide the user, like a JAMB official asking for your scores.
- **Line 2: `for subject in subjects:`** – Iterates over each subject in the `subjects` list. The variable `subject` takes each subject name (e.g., `"English"`, then `"Maths"`, etc.).
  - **Relatable Example**: It’s like a teacher calling out each subject on your JAMB slip to record your score.
- **Line 3: `score = input(f"Score for {subject}: ")`** – Prompts the user to enter a score for the current subject using an f-string for clarity (e.g., `Score for English:`).
  - **Relatable Example**: This is like filling out your JAMB scores on a form at a cybercafé.

```python
try:
    score = int(score)
    if score < 0 or score > 100:
        print(f"Invalid score for {subject}! Must be between 0 and 100. Skipping...")
        continue
```
- **Line 1: `try:`** – Starts a try-except block to handle invalid inputs (e.g., letters instead of numbers).
- **Line 2: `score = int(score)`** – Converts the input string to an integer. If it fails (e.g., user types “abc”), the `except` block runs.
- **Line 3: `if score < 0 or score > 100:`** – Checks if the score is invalid (outside 0–100, like JAMB’s scoring range).
- **Line 4: `print(...)`** – Informs the user the score is invalid, like a JAMB official rejecting a wrong entry.
- **Line 5: `continue`** – Skips the rest of the loop for this subject and moves to the next one.
  - **Relatable Example**: If you enter a score like 150 for English, it’s like a teacher saying, “This mark is impossible!” and moving to the next subject.

```python
if subject == "Physics" and score < 50:
    print(f"Physics score {score} is below 50! Stopping score entry.")
    break
```
- **Line 1: `if subject == "Physics" and score < 50:`** – Checks if the current subject is Physics and the score is below 50.
- **Line 2: `print(...)`** – Informs the user why the loop is stopping.
- **Line 3: `break`** – Stops the for loop entirely, skipping any remaining subjects.
  - **Relatable Example**: If you score below 50 in Physics, it’s like deciding to stop checking your JAMB results because you know Physics is your weakest subject.

```python
total_score += score
valid_scores_count += 1
```
- **Line 1: `total_score += score`** – Adds the valid score to `total_score`.
- **Line 2: `valid_scores_count += 1`** – Increments the count of valid scores.
  - **Relatable Example**: This is like adding up your JAMB scores on a calculator to get your total for university admission.

```python
except ValueError:
    print(f"Invalid input for {subject}! Please enter a number. Skipping...")
    continue
```
- **Line 1: `except ValueError:`** – Catches errors when the input can’t be converted to an integer (e.g., typing “abc”).
- **Line 2: `print(...)`** – Informs the user the input is invalid.
- **Line 3: `continue`** – Skips to the next subject.
  - **Relatable Example**: If you accidentally type your name instead of a score, it’s like a JAMB official saying, “Enter a number, not a name!” and moving on.

#### **Part 2: While Loop to Confirm Valid Scores**
```python
print("\nConfirming valid scores entered:")
count = 1
while count <= valid_scores_count:
    print(f"Valid score {count} recorded")
    count += 1
else:
    print("All scores checked!")
```
- **Line 1: `print(...)`** – Prints a header with a newline to separate sections.
- **Line 2: `count = 1`** – Initializes a variable to count valid scores, starting at 1.
- **Line 3: `while count <= valid_scores_count:`** – Loops as long as `count` is less than or equal to the number of valid scores.
  - **Relatable Example**: It’s like a teacher confirming how many subjects you scored correctly in your JAMB result.
- **Line 4: `print(f"Valid score {count} recorded")`** – Prints each valid score’s position (e.g., `Valid score 1 recorded`).
- **Line 5: `count += 1`** – Increments `count` to avoid an infinite loop.
- **Line 6: `else:`** – The `else` block runs when the loop finishes naturally (i.e., when `count > valid_scores_count`).
- **Line 7: `print("All scores checked!")`** – Confirms all valid scores were counted.
  - **Relatable Example**: This is like a teacher saying, “I’ve checked all your valid JAMB scores!” after reviewing your result slip.

#### **Part 3: Display Total Score and Feedback**
```python
print(f"\nTotal score: {total_score}")
if total_score > 250 and valid_scores_count == 4:
    print("Congratulations! Your score is above 250, great for many courses!")
elif valid_scores_count < 4:
    print("Not all subjects were scored. Try again to enter all scores.")
```
- **Line 1: `print(f"\nTotal score: {total_score}")`** – Prints the total score with a newline for clarity.
- **Line 2: `if total_score > 250 and valid_scores_count == 4:`** – Checks if the total score is above 250 (a good score for many university courses) and all 4 subjects were scored.
- **Line 3: `print(...)`** – Congratulates the user if conditions are met.
  - **Relatable Example**: It’s like getting a call from a university saying, “Your JAMB score qualifies you for Medicine!”
- **Line 4: `elif valid_scores_count < 4:`** – Checks if fewer than 4 subjects were scored (e.g., due to invalid inputs or breaking early).
- **Line 5: `print(...)`** – Encourages the user to try again.
  - **Relatable Example**: It’s like a JAMB official saying, “You didn’t complete all subjects; go back and enter them properly.”

### **Why It Works**
- The **for loop** iterates over subjects, collects scores, and uses `continue` to skip invalid inputs and `break` to stop if Physics is below 50, mimicking real-world JAMB scenarios.
- The **while loop** confirms the number of valid scores, reinforcing loop concepts and variable tracking.
- The program handles errors (e.g., non-numeric inputs) gracefully with try-except, making it robust for beginners.
- The feedback (congratulations or retry prompt) makes the program interactive and motivating, aligning with the **Pride Factor Rule**.

### **Relatable Nigerian Context**
This program feels like a real tool for a JAMB candidate checking their scores to see if they qualify for university. It’s like using a computer at a cybercafé to input your JAMB results and getting instant feedback. You can proudly show your friends, saying, “I built a JAMB score checker with Python!” It’s practical, relatable, and sparks conversations about university admissions.

---

## **Section 3 – Notes for Beginners**
- **Confidence-Building**: This project combines loops, input/output, and conditionals to create a useful tool. You start with simple steps (collecting inputs, checking conditions) and build something you can show off to classmates.
- **Common Mistake**: Forgetting to increment `count` in the while loop would cause an infinite loop, like a teacher endlessly checking the same score. Always ensure your loop variables update.
- **Next Steps**: Try extending the program to:
  - Allow users to retry invalid scores instead of skipping them.
  - Add specific feedback for each subject (e.g., “Great job in English!” for scores above 80).
  - Calculate the average score and suggest university courses based on the total.

This solution aligns with the **Pride Factor Rule**, giving you a program that’s fun, practical, and worth boasting about in a Nigerian context!