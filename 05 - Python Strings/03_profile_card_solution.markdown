# Solution to Python Weekly Project: Profile Card Generator

This document provides the solution to the Python weekly project from the Python Strings tutorial, where the task is to create a program that generates a formatted profile card using strings, with validation and manipulation. Below is the solution code, followed by a detailed explanation tailored for beginners.

---

## Solution Code

```python
# profile_card.py
# This program generates a formatted profile card using string manipulation

"""
Program: Profile Card Generator
Author: [Your Name]
Purpose: Creates a formatted profile card with string formatting, methods, and validation
"""

# Declare variables
full_name = "John Doe"  # String for full name
job_title = "Developer"  # String for job title
email = "john.doe@example.com"  # String for email
experience_years = 5  # Integer for years of experience
bio = """John Doe is a Developer
with 5 years of experience."""  # Multiline string for bio

# Print formatted profile card using f-strings
print("Profile Card:")
print(f"Name: {full_name}")
print(f"Job: {job_title.upper()}")
print(f"Email: {email}")
print(f"Experience: {experience_years} years")

# Print string manipulations
print("Email length:", len(email))  # Length of email
print("Is '@' in email?", "@" in email)  # Check for '@' in email
print("First 5 chars of name:", full_name[:5])  # First 5 characters of full_name
print("Bio lines:", bio.splitlines())  # Split bio into list of lines

# Validate types using isinstance()
print("Is full_name a string?", isinstance(full_name, str))
print("Is experience_years an integer?", isinstance(experience_years, int))
```

**Expected Output** (for `full_name = "John Doe"`, `job_title = "Developer"`, `email = "john.doe@example.com"`, `experience_years = 5`):
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

## Explanation

### Objective
The project requires creating a Python program (`profile_card.py`) that:
- Declares variables: `full_name` (string), `job_title` (string), `email` (string), `experience_years` (integer), and `bio` (multiline string).
- Prints a formatted card using f-strings combining all variables.
- Displays the length of `email`.
- Shows `job_title` in uppercase.
- Checks whether `"@"` is in `email`.
- Prints the first 5 characters of `full_name`.
- Splits `bio` into a list of lines.
- Uses `isinstance()` to validate `full_name` and `experience_years` types.
- Includes comments to explain each section.
- Runs correctly with `python profile_card.py`.

### Line-by-Line Breakdown
Let’s walk through the code to understand each part, its input, output, and purpose:

1. **File Creation**:
   - The code is saved in a file named `profile_card.py`. This ensures Python recognizes it as a Python script when you run `python profile_card.py`.

2. **Single-Line Comment**:
   ```python
   # profile_card.py
   # This program generates a formatted profile card using string manipulation
   ```
   - **Purpose**: These comments, marked with `#`, describe the file and program purpose. They are ignored by Python but help readers understand the code.
   - **Input**: None.
   - **Output**: None (comments don’t produce output).
   - **Side Effects**: None.

3. **Multiline Comment**:
   ```python
   """
   Program: Profile Card Generator
   Author: [Your Name]
   Purpose: Creates a formatted profile card with string formatting, methods, and validation
   """
   ```
   - **Purpose**: A multiline comment using triple quotes (`"""`) provides detailed documentation, including the program’s name, author, and purpose. Since it’s not assigned to a variable, Python ignores it.
   - **Input**: None.
   - **Output**: None.
   - **Side Effects**: None.

4. **Variable Declarations**:
   ```python
   full_name = "John Doe"  # String for full name
   job_title = "Developer"  # String for job title
   email = "john.doe@example.com"  # String for email
   experience_years = 5  # Integer for years of experience
   bio = """John Doe is a Developer
   with 5 years of experience."""  # Multiline string for bio
   ```
   - **Purpose**: Creates five variables:
     - `full_name`: Stores string `"John Doe"`. **Input**: `"John Doe"`. **Output**: None. **Side Effects**: `full_name` holds `"John Doe"`.
     - `job_title`: Stores string `"Developer"`. **Input**: `"Developer"`. **Output**: None. **Side Effects**: `job_title` holds `"Developer"`.
     - `email`: Stores string `"john.doe@example.com"`. **Input**: `"john.doe@example.com"`. **Output**: None. **Side Effects**: `email` holds `"john.doe@example.com"`.
     - `experience_years`: Stores integer `5`. **Input**: `5`. **Output**: None. **Side Effects**: `experience_years` holds `5`.
     - `bio`: Stores a multiline string with a line break. **Input**: Multiline text. **Output**: None. **Side Effects**: `bio` holds the text.
   - **Comment**: Inline comments explain each variable’s purpose.

5. **Formatted Profile Card**:
   ```python
   print("Profile Card:")
   print(f"Name: {full_name}")
   print(f"Job: {job_title.upper()}")
   print(f"Email: {email}")
   print(f"Experience: {experience_years} years")
   ```
   - **Purpose**: Prints a formatted card using f-strings.
   - **Line-by-Line**:
     - `print("Profile Card:")`: Prints the header. **Output**: `Profile Card:`.
     - `f"Name: {full_name}"`: Embeds `full_name`. **Output**: `Name: John Doe`.
     - `f"Job: {job_title.upper()}"`: Embeds uppercase `job_title`. **Output**: `Job: DEVELOPER`.
     - `f"Email: {email}"`: Embeds `email`. **Output**: `Email: john.doe@example.com`.
     - `f"Experience: {experience_years} years"`: Embeds `experience_years`. **Output**: `Experience: 5 years`.
   - **Side Effects**: Only printing.

6. **String Manipulations**:
   ```python
   print("Email length:", len(email))  # Length of email
   print("Is '@' in email?", "@" in email)  # Check for '@' in email
   print("First 5 chars of name:", full_name[:5])  # First 5 characters of full_name
   print("Bio lines:", bio.splitlines())  # Split bio into list of lines
   ```
   - **Purpose**: Performs string operations.
     - `len(email)`: Counts characters in `email`. **Input**: `email`. **Output**: `Email length: 20`.
     - `"@" in email`: Checks for `"@"`. **Input**: `"@"`, `email`. **Output**: `Is '@' in email? True`.
     - `full_name[:5]`: Slices first 5 characters. **Input**: `full_name`, `:5`. **Output**: `First 5 chars of name: John `.
     - `bio.splitlines()`: Splits at line breaks into a list. **Input**: `bio`. **Output**: `Bio lines: ['John Doe is a Developer', 'with 5 years of experience.']`.

7. **Type Validations**:
   ```python
   print("Is full_name a string?", isinstance(full_name, str))
   print("Is experience_years an integer?", isinstance(experience_years, int))
   ```
   - **Purpose**: Validates types.
     - `isinstance(full_name, str)`: Checks if `full_name` is a string. **Output**: `Is full_name a string? True`.
     - `isinstance(experience_years, int)`: Checks if `experience_years` is an integer. **Output**: `Is experience_years an integer? True`.

### Visual Description
When you run `python profile_card.py` in the terminal, the output is:
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
The profile card appears as a clean, multi-line format, followed by manipulation results and validations.

### Common Mistakes and Fixes
1. **Incorrect Slicing**:
   - **Mistake**:
     ```python
     print(full_name[5:])  # Wrong for first 5 chars
     ```
   - **Output**: `Doe`.
   - **Fix**: Use `full_name[:5]` for the first 5 characters.
2. **Forgetting F-String Prefix**:
   - **Mistake**:
     ```python
     print("Name: {full_name}")
     ```
   - **Output**: Literal `{full_name}`.
   - **Fix**: Use `f"Name: {full_name}"`.
3. **Invalid `isinstance()`**:
   - **Mistake**:
     ```python
     isinstance(full_name, "str")
     ```
   - **Error**: `TypeError: isinstance() arg 2 must be a type`.
   - **Fix**: Use `isinstance(full_name, str)`.
4. **Not Handling Multiline in Bio**:
   - **Mistake**: Using single quotes for `bio`.
   - **Error**: `SyntaxError`.
   - **Fix**: Use triple quotes (`"""`).
5. **Wrong File Extension**:
   - **Mistake**: Saving as `profile_card.txt`.
   - **Fix**: Save as `profile_card.py`.

### Validation Check
To confirm the program works:
1. Save the code in `profile_card.py`.
2. Open a terminal, navigate to the file’s directory, and run `python profile_card.py`.
3. Verify the output: formatted card, email length (`20`), `"@"` check (`True`), first 5 chars (`John `), bio lines (list of 2 strings), and type validations (`True`).
4. Test with different values (e.g., `full_name = "Jane Smith"`, `email = "jane@example.org"`) to ensure flexibility.
5. Add `print(type(bio.splitlines()))` to confirm it’s a list (`<class 'list'>`).

### Extension Idea Implementation
For learners interested in the extension ideas:
- **Add `is_valid_email`**:
  ```python
  is_valid_email = "@" in email and "." in email  # Check for '@' and '.'
  print("Is valid email?", is_valid_email)
  ```
  - Add after the `@` check. Outputs: `Is valid email? True`.
- **Replace spaces in `full_name`**:
  ```python
  name_no_spaces = full_name.replace(" ", "_")
  print("Name no spaces:", name_no_spaces)  # Outputs: John_Doe
  ```
  - Add after the slicing to get `John_Doe`.

### Research Prompts Answered
- **What are Unicode characters, and why are strings arrays of them?**
  - Unicode is a standard for encoding text from all languages (e.g., English, Chinese, emojis). Python strings are arrays of Unicode code points, allowing seamless handling of international text without byte-level concerns.
- **How does `strip()` differ from `lstrip()` and `rstrip()`?**
  - `strip()` removes whitespace from both ends.
  - `lstrip()` removes from the left (leading).
  - `rstrip()` removes from the right (trailing).

### One-Line Takeaway
This program generates a formatted profile card using f-strings, string methods like `upper()` and `splitlines()`, slicing, substring checks, and type validation with `isinstance()`.