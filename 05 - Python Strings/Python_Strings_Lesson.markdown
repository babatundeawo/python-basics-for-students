# Instructional Guide for Python Strings

Below is a structured guide for teaching complete beginners about **Python Strings**, based on the provided lesson. The content is tailored to be clear, concise, and progressive, adhering to the specified instructional format.

---

## Section 1 – Explanations

The lesson introduces **Python strings**, which are sequences of characters used to represent text. Strings are enclosed in either single quotes (`'`) or double quotes (`"`), and both forms are equivalent. For example, `'hello'` and `"hello"` are the same. Strings are versatile and can be manipulated in various ways, as outlined below.

1. **Basic String Operations**:
   - You can print a string using the `print()` function:
     ```python
     print("Hello")  # Outputs: Hello
     print('Hello')  # Outputs: Hello
     ```
   - Quotes inside strings are allowed if they differ from the surrounding quotes:
     ```python
     print("It's alright")  # Outputs: It's alright
     print('He is called "Johnny"')  # Outputs: He is called "Johnny"
     ```

2. **Assigning Strings to Variables**:
   - Strings can be stored in variables using the assignment operator (`=`):
     ```python
     a = "Hello"
     print(a)  # Outputs: Hello
     ```

3. **Multiline Strings**:
   - Use triple quotes (`"""` or `'''`) to create strings that span multiple lines:
     ```python
     a = """Lorem ipsum dolor sit amet,
     consectetur adipiscing elit."""
     print(a)  # Outputs the text with line breaks preserved
     ```

4. **Strings as Arrays**:
   - Strings are treated as arrays of characters, where each character has an index starting at 0. You can access a character using square brackets:
     ```python
     a = "Hello, World!"
     print(a[1])  # Outputs: e (character at index 1)
     ```

5. **Looping Through Strings**:
   - You can iterate over each character in a string using a `for` loop:
     ```python
     for x in "banana":
         print(x)  # Outputs each letter on a new line: b, a, n, a, n, a
     ```

6. **String Length**:
   - The `len()` function returns the number of characters in a string:
     ```python
     a = "Hello, World!"
     print(len(a))  # Outputs: 13
     ```

7. **Checking Strings**:
   - Use the `in` keyword to check if a substring exists within a string:
     ```python
     txt = "The best things in life are free!"
     print("free" in txt)  # Outputs: True
     ```
   - Use `not in` to check if a substring is absent:
     ```python
     print("expensive" not in txt)  # Outputs: True
     ```

8. **String Slicing**:
   - Extract a portion of a string using slice notation `[start:end]`:
     ```python
     b = "Hello, World!"
     print(b[2:5])  # Outputs: llo (characters from index 2 to 4)
     print(b[:5])   # Outputs: Hello (from start to index 4)
     print(b[2:])   # Outputs: llo, World! (from index 2 to end)
     print(b[-5:-2])  # Outputs: orl (negative indexing from end)
     ```

9. **Modifying Strings**:
   - Strings have built-in methods like:
     - `upper()`: Converts to uppercase.
     - `lower()`: Converts to lowercase.
     - `strip()`: Removes leading/trailing whitespace.
     - `replace()`: Replaces a substring with another.
     - `split()`: Splits a string into a list based on a separator.
     ```python
     a = " Hello, World! "
     print(a.upper())      # Outputs: HELLO, WORLD!
     print(a.lower())      # Outputs: hello, world!
     print(a.strip())      # Outputs: Hello, World!
     print(a.replace("H", "J"))  # Outputs: Jello, World!
     print(a.split(","))   # Outputs: [' Hello', ' World! ']
     ```

10. **String Concatenation**:
    - Combine strings using the `+` operator:
      ```python
      a = "Hello"
      b = "World"
      c = a + " " + b
      print(c)  # Outputs: Hello World
      ```

11. **String Formatting with F-Strings**:
    - F-strings allow embedding variables or expressions inside strings using `{}`:
      ```python
      age = 36
      txt = f"My name is John, I am {age}"
      print(txt)  # Outputs: My name is John, I am 36
      price = 59
      txt = f"The price is {price:.2f} dollars"
      print(txt)  # Outputs: The price is 59.00 dollars
      ```

12. **Escape Characters**:
    - Use a backslash (`\`) to include special characters:
      ```python
      txt = "We are the so-called \"Vikings\" from the north."
      print(txt)  # Outputs: We are the so-called "Vikings" from the north.
      ```
    - Common escape characters include `\n` (new line), `\t` (tab), and `\\` (backslash).

---

## Section 2 – Class Exercise

**Exercise: Personalized Greeting Card**

**Problem**: You’re creating a simple greeting card generator. Ask the user for their name and a short message. Then, create a formatted greeting that uses string concatenation, slicing, and an f-string to personalize the card. Check if the word "happy" is in the message and print a response if it is.

**Guidelines**:
1. Use `input()` to collect the user’s name and message (assume prior knowledge of `input()`).
2. Create a greeting using an f-string that includes the user’s name and the first 5 characters of their message.
3. Concatenate a fixed string like "Best wishes!" to the greeting.
4. Check if "happy" is in the message using the `in` keyword and print "What a joyful message!" if it is.
5. Test your program with different inputs to ensure it works.

**Example Interaction**:
```
Enter your name: Alice
Enter your message: Happy birthday!
Greeting: Dear Alice, your message starts with: Happy. Best wishes!
What a joyful message!
```

---

## Section 3 – Weekly Project

**Project: Simple Contact Card Generator**

**Project Brief**: Create a program that generates a formatted contact card for a user based on their input. The card should include their name, email, and a short bio. Use string methods, concatenation, and f-strings to format the output neatly, and introduce the concept of string length to ensure the bio isn’t too long. This project encourages creativity and prepares students for future lessons on lists or user input validation.

**Guidelines**:
1. Ask the user to input their full name, email address, and a short bio (e.g., hobbies or interests).
2. Use string methods:
   - Convert the name to title case using `title()`.
   - Strip any extra whitespace from the email using `strip()`.
   - Check the length of the bio using `len()` and ensure it’s under 50 characters. If it’s too long, slice it to the first 50 characters.
3. Create a formatted contact card using an f-string, combining the name, email, and bio.
4. Concatenate a header like "=== Contact Card ===" and a footer like "=== End ===".
5. Print the card and the length of the bio.
6. **Exploration Prompt**: Experiment with other string methods like `upper()` or `replace()` to customize the card further. How could you handle multiple contacts in the future? (This hints at lists, a future topic.)

**Example Output**:
```
Enter your full name: john doe
Enter your email:  johndoe@example.com 
Enter your bio: I love coding and hiking in the mountains.
=== Contact Card ===
Name: John Doe
Email: johndoe@example.com
Bio: I love coding and hiking in the mountains.
Bio length: 39 characters
=== End ===
```

**Tips**:
- Use `input()` to collect data.
- Test with different inputs, including long bios to check slicing.
- Be creative with formatting to make the card visually appealing.