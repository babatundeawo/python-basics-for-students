# Solution to Personalized Greeting Card Exercise

This document provides the solution to the **Personalized Greeting Card** exercise from the Python Strings lesson. The exercise involves creating a program that takes a user's name and message, formats a greeting using string concatenation, slicing, and f-strings, and checks if the word "happy" is in the message. Below is the explanation and the complete solution.

## Explanation

The exercise requires a program that:
1. Collects the user’s name and message using `input()`.
2. Creates a greeting using an f-string that includes the user’s name and the first 5 characters of their message (using string slicing).
3. Concatenates a fixed string ("Best wishes!") to the greeting.
4. Checks if the word "happy" is in the message using the `in` keyword and prints a response if it is.
5. Outputs the formatted greeting and any additional message.

### Step-by-Step Breakdown
- **Step 1: Collect User Input**
  - Use `input()` to prompt the user for their name and message.
  - Store the inputs in variables (e.g., `name` and `message`).
- **Step 2: Create the Greeting**
  - Use an f-string to format the greeting, incorporating the user’s `name` and the first 5 characters of `message` (using slicing: `message[:5]`).
  - Concatenate the string "Best wishes!" using the `+` operator to complete the greeting.
- **Step 3: Check for "happy"**
  - Use the `in` keyword to check if "happy" is in the `message`.
  - If "happy" is present, print "What a joyful message!".
- **Step 4: Output the Results**
  - Print the formatted greeting.
  - Print the joyful message response if applicable.

### Key Concepts Used
- **Input**: `input()` to get user data.
- **F-Strings**: For embedding variables in the greeting (`f"Dear {name}, ..."`).
- **String Slicing**: To extract the first 5 characters (`message[:5]`).
- **String Concatenation**: To append "Best wishes!" (`+`).
- **String Checking**: Using `in` to check for "happy".
- **Conditional Statements**: Using `if` to print the joyful message conditionally.

This solution is designed to be simple and confidence-building, using only the string concepts covered in the lesson.

## Solution Code

```python
# Get user input for name and message
name = input("Enter your name: ")
message = input("Enter your message: ")

# Create the greeting using an f-string and slicing
greeting = f"Dear {name}, your message starts with: {message[:5]}. Best wishes!"

# Print the greeting
print(greeting)

# Check if "happy" is in the message (case-sensitive)
if "happy" in message:
    print("What a joyful message!")
```

### Example Output
**Input**:
```
Enter your name: Alice
Enter your message: Happy birthday!
```

**Output**:
```
Greeting: Dear Alice, your message starts with: Happy. Best wishes!
What a joyful message!
```

**Input**:
```
Enter your name: Bob
Enter your message: Wishing you well!
```

**Output**:
```
Greeting: Dear Bob, your message starts with: Wishi. Best wishes!
```

### Notes
- The solution assumes the user has basic familiarity with `input()` from prior lessons, as implied by the exercise guidelines.
- The check for "happy" is case-sensitive (e.g., "Happy" won’t match). For beginners, this keeps the logic simple, but you could explore `message.lower()` in future lessons to handle case-insensitivity.
- If the message is shorter than 5 characters, slicing (`message[:5]`) will safely return the entire message.
- Test the program with various inputs, such as short messages, messages with "happy," and messages without it, to ensure it works as expected.

This solution reinforces string manipulation skills while keeping the task engaging and practical for beginners.