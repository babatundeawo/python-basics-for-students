# Python RegEx Weekly Project: Email Validator Solution and Explanation

This Markdown file provides the solution to the weekly project from the Python RegEx teaching package, which involves creating a simple **Email Validator** using Python’s `re` module. The solution includes a complete, beginner-friendly script with detailed explanations, adhering to the instructional framework for clarity and hands-on learning. The project focuses on validating email addresses, handling user input, and providing meaningful feedback.

---

## Project Overview
The goal is to create a Python script that validates whether a user-provided string is a valid email address using a RegEx pattern. The script should:
- Accept user input.
- Check if the input matches a valid email pattern.
- Provide feedback on whether the email is valid or invalid, with reasons for invalid cases.
- Include comments explaining the RegEx pattern.

---

## Solution

Below is the complete Python script for the Email Validator.

```python
import re

# RegEx pattern for email validation
# Matches: local-part@domain.tld (e.g., user.name@domain.com)
pattern = r"^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$"

def validate_email(email):
    """
    Validates an email address using RegEx.
    Returns a tuple: (is_valid, message)
    """
    # Check if the email matches the pattern
    match = re.search(pattern, email)
    
    if match:
        return True, "Valid email"
    else:
        # Check for common issues
        if "@" not in email:
            return False, "Invalid email: Missing '@' symbol"
        if "." not in email.split("@")[-1]:
            return False, "Invalid email: Missing domain extension (e.g., .com)"
        if not email.split("@")[0]:
            return False, "Invalid email: Missing local part before '@'"
        return False, "Invalid email: Does not match valid email format"

# Main program
print("Email Validator: Enter an email address to validate (or 'quit' to exit)")
while True:
    user_input = input("Enter email: ").strip()
    
    if user_input.lower() == "quit":
        print("Exiting program.")
        break
    
    is_valid, message = validate_email(user_input)
    print(message)

```

---

## Explanation

### Learning Goals
- Understand how to construct a RegEx pattern for email validation.
- Use `re.search()` to check for pattern matches.
- Handle user input and provide clear feedback.
- Apply metacharacters, sets, and anchors in a practical context.

### Code Breakdown
Here’s a line-by-line explanation of the script, focusing on clarity for beginners.

#### RegEx Pattern
```python
pattern = r"^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$"
```
- **Purpose**: Defines the pattern for a valid email (e.g., `user@domain.com`).
- **Components**:
  - `^`: Ensures the string starts at the beginning.
  - `[a-zA-Z0-9._%+-]+`: Matches one or more characters in the local part (before `@`). Allowed characters:
    - Letters (`a-z`, `A-Z`)
    - Digits (`0-9`)
    - Special characters (`.`, `_`, `%`, `+`, `-`)
  - `@`: Matches the literal `@` symbol.
  - `[a-zA-Z0-9.-]+`: Matches one or more characters in the domain (e.g., `domain` in `domain.com`). Allows:
    - Letters and digits
    - Dots (`.`) and hyphens (`-`)
  - `\.`: Matches a literal dot (for the domain extension, e.g., `.com`).
  - `[a-zA-Z]{2,}`: Matches two or more letters for the top-level domain (e.g., `com`, `org`).
  - `$`: Ensures the string ends after the pattern.
- **Why raw string (`r"..."`)?**: Prevents backslashes (e.g., `\.`) from being misinterpreted.

**Visual Description**: The pattern ensures the email has a local part, an `@` symbol, a domain, and a valid extension (e.g., `.com`). It rejects malformed emails like `user@domain` or `user.domain.com`.

#### Function: `validate_email`
```python
def validate_email(email):
    """
    Validates an email address using RegEx.
    Returns a tuple: (is_valid, message)
    """
    match = re.search(pattern, email)
    
    if match:
        return True, "Valid email"
    else:
        if "@" not in email:
            return False, "Invalid email: Missing '@' symbol"
        if "." not in email.split("@")[-1]:
            return False, "Invalid email: Missing domain extension (e.g., .com)"
        if not email.split("@")[0]:
            return False, "Invalid email: Missing local part before '@'"
        return False, "Invalid email: Does not match valid email format"
```
- **Purpose**: Validates the input email and provides feedback.
- **Line-by-Line**:
  - `match = re.search(pattern, email)`: Uses `re.search()` to check if `email` matches the pattern. Returns a Match Object or `None`.
  - `if match:`: If a match is found, returns `(True, "Valid email")`.
  - `else:`: If no match, checks for specific issues:
    - `if "@" not in email`: Checks for missing `@`.
    - `if "." not in email.split("@")[-1]`: Ensures the domain has an extension (e.g., `.com`).
    - `if not email.split("@")[0]`: Ensures the local part (before `@`) exists.
    - Default: Returns a generic invalid message for other issues.
- **Output**: A tuple `(is_valid, message)` where `is_valid` is a boolean and `message` explains the result.

**Common Mistake**: Not checking specific failure cases, leading to vague feedback.
- **Fix**: Include targeted checks (like missing `@` or `.`) to help users understand why an email is invalid.

#### Main Program
```python
print("Email Validator: Enter an email address to validate (or 'quit' to exit)")
while True:
    user_input = input("Enter email: ").strip()
    
    if user_input.lower() == "quit":
        print("Exiting program.")
        break
    
    is_valid, message = validate_email(user_input)
    print(message)
```
- **Purpose**: Handles user interaction in a loop.
- **Line-by-Line**:
  - `print(...)`: Displays instructions.
  - `while True:`: Runs until the user types "quit".
  - `user_input = input("Enter email: ").strip()`: Gets user input and removes leading/trailing spaces.
  - `if user_input.lower() == "quit"`: Checks for exit condition (case-insensitive).
  - `is_valid, message = validate_email(user_input)`: Calls the validation function.
  - `print(message)`: Outputs the result.

**Visual Description**: The program prompts the user, validates each input, and prints whether it’s valid or why it’s invalid. It continues until the user types "quit".

**Expected Output** (example interaction):
```
Email Validator: Enter an email address to validate (or 'quit' to exit)
Enter email: user@domain.com
Valid email
Enter email: user@domain
Invalid email: Missing domain extension (e.g., .com)
Enter email: @domain.com
Invalid email: Missing local part before '@'
Enter email: user.domain.com
Invalid email: Missing '@' symbol
Enter email: quit
Exiting program.
```

**Common Mistake**: Not handling empty inputs or extra spaces.
- **Fix**: Use `.strip()` to clean input and check for empty strings if needed.

### Validation Checks
- Test with valid emails: `user@domain.com`, `name.surname@sub.domain.org`.
- Test with invalid emails:
  - `user@domain` (missing extension).
  - `@domain.com` (missing local part).
  - `user.domain.com` (missing `@`).
  - `user@@domain.com` (invalid format).
- Confirm feedback messages are clear and specific.

---

## Assessment Criteria
- **Correctness**: The pattern correctly validates emails like `user@domain.com` and rejects invalid ones. The script handles edge cases with appropriate messages.
- **Clarity**: The code includes comments explaining the pattern and logic. Output messages are user-friendly.
- **Completeness**: The script accepts input, validates it, and provides feedback in a loop until the user quits.

**Common Pitfalls**:
- Using a too-simplistic pattern (e.g., `.*@.*\..*`) that accepts invalid emails.
  - **Fix**: Use a precise pattern like the one provided, with specific character sets and anchors.
- Not escaping the dot (`\.`) in the pattern, which could match any character.
  - **Fix**: Always escape special characters when they should be literal.
- Failing to test with varied inputs, missing edge cases.
  - **Fix**: Test with valid and invalid emails, including unusual cases.

---

## Extension Ideas
- **Complex Emails**: Extend the pattern to support subdomains (e.g., `user@sub.domain.co.uk`) by allowing multiple dots in the domain.
- **Loop Counter**: Add a counter to track how many valid emails were entered before quitting.
- **Case Sensitivity**: Allow case-insensitive local parts while enforcing lowercase domains.

**Example Pattern for Extension** (not a full solution):
- `[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}(\.[a-zA-Z]{2,})?` to support `co.uk`.

---

## Completion Checklist
- [ ] The script validates emails using a correct RegEx pattern.
- [ ] The pattern is commented and explained.
- [ ] The program handles user input in a loop and exits on "quit".
- [ ] Feedback messages are specific and helpful for invalid cases.
- [ ] Tested with at least five different inputs (valid and invalid).
- [ ] Avoided common pitfalls like unescaped characters or vague error messages.

**One-Line Takeaway**: The Email Validator uses a RegEx pattern with `re.search()` to validate email formats, providing clear feedback to help users correct invalid inputs.