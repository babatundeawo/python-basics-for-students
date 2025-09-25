# Solution: Simple Greeting Generator Exercise

This section provides the solution to the **Class Exercise: Build a Simple Greeting Generator** from the Python Strings lesson. The exercise asked you to create a program that prompts the user for their name and favorite activity, then prints a personalized greeting using string operations, ensuring the name is capitalized. Below is the explanation and the complete solution, designed to reinforce string concepts for beginners.

## Explanation

The goal of the exercise is to create a program that:
1. Uses `input()` to collect the user’s name and favorite activity.
2. Stores these inputs in variables.
3. Uses the `capitalize()` method to ensure the name starts with a capital letter.
4. Combines the inputs into a greeting using an f-string.
5. Prints the greeting, like: "Hi, Sarah! I hear you love reading."

### Step-by-Step Breakdown
- **Step 1: Collecting Input**  
  The `input()` function prompts the user to enter text, which we store in variables. For example, `name = input("Enter your name: ")` captures the user’s name as a string.

- **Step 2: Capitalizing the Name**  
  The `capitalize()` method converts the first character of a string to uppercase and the rest to lowercase. This ensures the name looks proper, e.g., "sarah" becomes "Sarah".

- **Step 3: Creating the Greeting**  
  An f-string (`f"..."`) lets us embed variables directly into a string using curly braces `{}`. We combine the capitalized name and activity into a friendly message.

- **Step 4: Printing the Result**  
  The `print()` function outputs the final greeting to the console.

This solution uses concepts from the Python Strings lesson, including variables, `input()`, string methods (`capitalize()`), and f-strings, making it a practical application of string manipulation.

### Solution Code
Here’s the complete Python code for the greeting generator:

```python
# Ask the user for their name and store it
name = input("Enter your name: ")

# Ask the user for their favorite activity and store it
activity = input("Enter your favorite activity: ")

# Capitalize the name to ensure proper formatting
name = name.capitalize()

# Create a personalized greeting using an f-string
greeting = f"Hi, {name}! I hear you love {activity}."

# Print the greeting
print(greeting)
```

### How It Works
- The program prompts the user to enter their name (e.g., "sarah").
- It then asks for their favorite activity (e.g., "reading").
- The `capitalize()` method transforms the name to "Sarah".
- The f-string combines the capitalized name and activity into a sentence.
- The `print()` function displays the result, such as:  
  ```
  Enter your name: sarah
  Enter your favorite activity: reading
  Hi, Sarah! I hear you love reading.
  ```

### Why This Matters
This exercise shows how strings can be used to create interactive, personalized programs. By combining user input, string methods, and f-strings, you can build programs that feel dynamic and engaging, like a greeting card generator or a chatbot. These skills are building blocks for more complex programs, such as forms or story generators.

### Try It Yourself
Run the code and test it with different names and activities. Experiment by:
- Adding a second activity and including it in the greeting.
- Using `strip()` to remove extra spaces if the user types them.
- Trying other string methods, like `upper()` for a fun, shouting greeting!

This solution reinforces the core string concepts from the lesson while encouraging you to practice and explore further.