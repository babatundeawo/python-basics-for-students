# Python Strings for Beginners

This tutorial covers Python strings, including their creation, manipulation, slicing, concatenation, formatting, escape characters, and common string methods. Below is a beginner-friendly teaching package based on the provided lesson note, designed to guide learners toward intermediate-level mastery with practical examples and exercises.

---

## Section 1 — Topical Explanations

### Learning Goals
- Understand how to create and assign strings using single or double quotes.
- Learn to work with multiline strings, string indexing, and looping.
- Master string slicing, concatenation, and formatting (f-strings).
- Explore string methods like `upper()`, `lower()`, `strip()`, `replace()`, and `split()`.
- Understand escape characters and how to check for substrings using `in` and `not in`.

### Creating and Assigning Strings
Strings in Python are sequences of Unicode characters enclosed in single (`'`) or double (`"`) quotes. Both are equivalent.

**Example Code**:
```python
# Using single and double quotes
greeting1 = "Hello"
greeting2 = 'Hello'
print(greeting1)  # Outputs: Hello
print(greeting2)  # Outputs: Hello
```
- **Line-by-Line Explanation**:
  - `greeting1 = "Hello"`: Assigns string `"Hello"` to `greeting1`. **Input**: `"Hello"`. **Output**: None. **Side Effects**: `greeting1` holds `"Hello"`.
  - `greeting2 = 'Hello'`: Assigns string `'Hello'` to `greeting2`. **Input**: `'Hello'`. **Output**: None. **Side Effects**: `greeting2` holds `'Hello'`.
  - `print(greeting1)`: Displays `Hello`. **Input**: `greeting1`. **Output**: `Hello`.
  - Similarly for `greeting2`.
- **Visual Description**: Terminal shows `Hello` on two lines.
- **Common Mistake**: Mixing quote types incorrectly, e.g., `"Hello'`.
  - **Error**: `SyntaxError: EOL while scanning string literal`.
  - **Fix**: Use matching quotes, e.g., `"Hello"` or `'Hello'`.
- **Validation Check**: Print the string to confirm it displays correctly.

### Quotes Inside Quotes
You can include quotes in a string if they differ from the enclosing quotes.

**Example Code**:
```python
print("It's alright")  # Outputs: It's alright
print("He is called 'Johnny'")  # Outputs: He is called 'Johnny'
print('He is called "Johnny"')  # Outputs: He is called "Johnny"
```
- **Explanation**:
  - Single quotes (`'`) can be used inside double-quoted strings, and vice versa.
- **Common Mistake**: Using same quotes inside, e.g., `"He is "Johnny""`.
  - **Error**: `SyntaxError`.
  - **Fix**: Use different quotes or escape characters (see below).

### Multiline Strings
Use triple quotes (`"""` or `'''`) for strings spanning multiple lines.

**Example Code**:
```python
poem = """Roses are red,
Violets are blue,
Python is fun,
And so are you!"""
print(poem)
```
- **Explanation**:
  - `poem = """..."""`: Assigns a multiline string. Line breaks are preserved.
  - **Output**:
    ```
    Roses are red,
    Violets are blue,
    Python is fun,
    And so are you!
    ```
- **Common Mistake**: Using single/double quotes for multiline strings.
  - **Error**: `SyntaxError`.
  - **Fix**: Use triple quotes.
- **Validation Check**: Check that line breaks appear in the output.

### Strings as Arrays
Strings are arrays of Unicode characters. Each character has an index (starting at `0`). Use square brackets `[]` to access characters.

**Example Code**:
```python
text = "Hello, World!"
print(text[1])  # Outputs: e
```
- **Explanation**:
  - `text[1]`: Accesses the character at index `1` (`e`). **Input**: `1`. **Output**: `e`.
- **Common Mistake**: Accessing an out-of-range index, e.g., `text[50]`.
  - **Error**: `IndexError: string index out of range`.
  - **Fix**: Ensure the index is within `0` to `len(text)-1`.

### Looping Through Strings
Since strings are arrays, you can loop through characters using a `for` loop.

**Example Code**:
```python
for char in "banana":
    print(char)
```
- **Explanation**:
  - Loops through each character in `"banana"`. **Output**:
    ```
    b
    a
    n
    a
    n
    a
    ```
- **Common Mistake**: Forgetting indentation in the loop body.
  - **Error**: `IndentationError`.
  - **Fix**: Indent the `print` statement.

### String Length
Use `len()` to get the number of characters in a string.

**Example Code**:
```python
text = "Hello, World!"
print(len(text))  # Outputs: 13
```
- **Explanation**:
  - `len(text)`: Counts characters, including spaces and punctuation. **Input**: `text`. **Output**: `13`.
- **Common Mistake**: Forgetting parentheses in `len()`.
  - **Error**: `TypeError: 'int' object is not callable`.
  - **Fix**: Use `len(text)`.

### Checking Substrings
Use `in` to check if a substring exists, and `not in` to check if it doesn’t.

**Example Code**:
```python
txt = "The best things in life are free!"
print("free" in txt)  # Outputs: True
if "free" in txt:
    print("Yes, 'free' is present.")
if "expensive" not in txt:
    print("No, 'expensive' is NOT present.")
```
- **Explanation**:
  - `"free" in txt`: Returns `True` because `"free"` is in `txt`.
  - `"expensive" not in txt`: Returns `True` because `"expensive"` is absent.
  - **Output**:
    ```
    True
    Yes, 'free' is present.
    No, 'expensive' is NOT present.
    ```
- **Common Mistake**: Using `in` with non-strings, e.g., `5 in txt`.
  - **Error**: `TypeError`.
  - **Fix**: Ensure the left operand is a string.

### String Slicing
Use slice syntax `[start:end]` to extract a substring. The `end` index is excluded.

**Example Code**:
```python
b = "Hello, World!"
print(b[2:5])  # Outputs: llo
print(b[:5])  # Outputs: Hello
print(b[2:])  # Outputs: llo, World!
print(b[-5:-2])  # Outputs: rld
```
- **Explanation**:
  - `b[2:5]`: Extracts characters from index `2` to `4` (`llo`).
  - `b[:5]`: From start to index `4` (`Hello`).
  - `b[2:]`: From index `2` to end (`llo, World!`).
  - `b[-5:-2]`: From index `-5` (`r`) to `-3` (`rld`).
- **Common Mistake**: Using invalid indices, e.g., `b[10:5]`.
  - **Fix**: Ensure `start` <= `end`.

### String Modification
Python provides methods like `upper()`, `lower()`, `strip()`, `replace()`, and `split()`. These return new strings, leaving the original unchanged.

**Example Code**:
```python
a = " Hello, World! "
print(a.upper())  # Outputs: HELLO, WORLD!
print(a.lower())  # Outputs: hello, world!
print(a.strip())  # Outputs: Hello, World!
print(a.replace("H", "J"))  # Outputs: Jello, World!
print(a.split(","))  # Outputs: [' Hello', ' World! ']
```
- **Explanation**:
  - `upper()`: Converts to uppercase.
  - `lower()`: Converts to lowercase.
  - `strip()`: Removes leading/trailing whitespace.
  - `replace("H", "J")`: Replaces `"H"` with `"J"`.
  - `split(",")`: Splits at `,` into a list.
- **Common Mistake**: Assuming methods modify the original string.
  - **Fix**: Assign the result, e.g., `a = a.upper()`.

### String Concatenation
Use `+` to combine strings.

**Example Code**:
```python
a = "Hello"
b = "World"
c = a + " " + b
print(c)  # Outputs: Hello World
```
- **Explanation**:
  - `a + " " + b`: Concatenates `"Hello"`, a space, and `"World"`.
- **Common Mistake**: Concatenating strings with numbers, e.g., `"Hello" + 5`.
  - **Error**: `TypeError: can only concatenate str to str`.
  - **Fix**: Convert numbers to strings, e.g., `"Hello" + str(5)`.

### String Formatting (F-Strings)
F-strings (Python 3.6+) use `f` prefix and `{}` placeholders for variables or expressions.

**Example Code**:
```python
age = 36
price = 59
txt = f"My name is John, I am {age}"
print(txt)  # Outputs: My name is John, I am 36
print(f"The price is {price:.2f} dollars")  # Outputs: The price is 59.00 dollars
print(f"The price is {20 * price} dollars")  # Outputs: The price is 1180 dollars
```
- **Explanation**:
  - `f"My name is John, I am {age}"`: Embeds `age` (`36`).
  - `{price:.2f}`: Formats `price` to 2 decimal places.
  - `{20 * price}`: Embeds the result of `20 * 59`.
- **Common Mistake**: Forgetting the `f` prefix.
  - **Error**: `{age}` treated as literal text.
  - **Fix**: Use `f` before the string.

### Escape Characters
Use `\` to insert special characters, like quotes inside quotes.

**Example Code**:
```python
txt = "We are the so-called \"Vikings\" from the north."
print(txt)  # Outputs: We are the so-called "Vikings" from the north.
print("Line1\nLine2")  # Outputs: Line1 (new line) Line2
print("Tab\tSpace")  # Outputs: Tab    Space
```
- **Explanation**:
  - `\"`: Escapes a double quote.
  - `\n`: Adds a new line.
  - `\t`: Adds a tab.
- **Common Mistake**: Using a single backslash in paths, e.g., `C:\new`.
  - **Error**: `SyntaxError` (invalid escape).
  - **Fix**: Use raw strings (`r"C:\new"`) or double backslashes (`"C:\\new"`).

### String Methods
Python offers many string methods (e.g., `startswith()`, `endswith()`, `count()`). They return new values without modifying the original string.

**Example Code**:
```python
text = "Hello, World!"
print(text.startswith("He"))  # Outputs: True
print(text.endswith("!"))  # Outputs: True
print(text.count("l"))  # Outputs: 3
```
- **Explanation**:
  - `startswith("He")`: Checks if string starts with `"He"`.
  - `endswith("!")`: Checks if string ends with `"!"`.
  - `count("l")`: Counts occurrences of `"l"`.

**One-Line Takeaway**: Python strings are versatile arrays of characters, supporting slicing, concatenation, formatting, and methods like `upper()`, `strip()`, and `split()`.

---

## Section 2 — Class Exercise

### Exercise: String Manipulator

**Objective**: Write a Python program that manipulates strings using slicing, concatenation, formatting, and methods.

**Step-by-Step Instructions**:
1. Create a file named `strings.py`.
2. Declare variables:
   - `greeting` (string, e.g., `"Hello, Python!"`).
   - `name` (string, e.g., `"Alice"`).
   - `score` (integer, e.g., `95`).
3. Create a multiline string `message` describing the user (e.g., name and score).
4. Print:
   - The second character of `greeting`.
   - A slice of `greeting` from index `7` to `12`.
   - `greeting` in uppercase.
   - `name` and `score` using an f-string.
   - Whether `"Python"` is in `greeting`.
   - The `message` with leading/trailing whitespace removed.
5. Add comments to explain each step.
6. Run the program with `python strings.py`.

**Hints**:
- Use `greeting[1]` for the second character.
- Use f-strings for formatting, e.g., `f"Score: {score}"`.
- Use `strip()` for whitespace.

**Checkpoint**:
- Check if the output shows correct values and manipulations.
- Verify `"Python" in greeting` returns `True`.

**Example Output** (for `greeting = "Hello, Python!"`, `name = "Alice"`, `score = 95`):
```
Second character: e
Slice (7 to 12): Python
Uppercase greeting: HELLO, PYTHON!
Formatted string: Alice scored 95 points
Is 'Python' in greeting? True
Cleaned message: Alice has a score of 95
```

---

## Section 3 — Weekly Project

### Project: Profile Card Generator

**Objective**: Create a Python program that generates a formatted profile card using strings, with validation and manipulation.

**Milestones**:
1. Create a file named `profile_card.py`.
2. Declare variables:
   - `full_name` (string, e.g., `"John Doe"`).
   - `job_title` (string, e.g., `"Developer"`).
   - `email` (string, e.g., `"john.doe@example.com"`).
   - `experience_years` (integer, e.g., `5`).
3. Create a multiline string `bio` describing the user.
4. Print:
   - A formatted card using f-strings combining `full_name`, `job_title`, `email`, and `experience_years`.
   - The length of `email`.
   - `job_title` in uppercase.
   - Whether `"@"` is in `email`.
   - The first 5 characters of `full_name`.
   - `bio` split into a list of lines.
5. Use `isinstance()` to validate `full_name` and `experience_years` types.
6. Add comments to explain each section.

**Deliverables**:
- A working `profile_card.py` file.
- Output showing the formatted card, manipulations, and validations.

**Research Prompts**:
- What are Unicode characters, and why are strings arrays of them?
- How does `strip()` differ from `lstrip()` and `rstrip()`?

**Assessment Criteria**:
- Code runs without errors.
- Strings are manipulated correctly (slicing, methods, formatting).
- Output includes all required components.
- Comments explain key steps.
- Type validations are correct.

**Extension Idea**:
- Add a boolean `is_valid_email` (check if `email` contains `"@"` and `"."`).
- Replace spaces in `full_name` with underscores.

**Example Output** (example for `full_name = "John Doe"`, `job_title = "Developer"`, `email = "john.doe@example.com"`, `experience_years = 5`):
```
Profile Card:
Name: John Doe
Job: DEVELOPER
Email: john.doe@example.com
Experience: 5 years
Email length: 20
Is '@' in email? True
First 5 chars of name: John 
Bio lines: ['John Doe is a Developer', 'with 5 years of experience.']
Is full_name a string? True
Is experience_years an integer? True
```

---

## Completion Checklist
- [ ] Understood string creation with single/double/triple quotes.
- [ ] Used indexing, slicing, and looping with strings.
- [ ] Applied string methods (`upper()`, `strip()`, etc.).
- [ ] Performed concatenation and f-string formatting.
- [ ] Used escape characters and checked substrings with `in`/`not in`.
- [ ] Completed the class exercise and verified the output.
- [ ] Started the weekly project and planned the profile card.
- [ ] Fixed at least one common mistake (e.g., incorrect quotes or invalid index).