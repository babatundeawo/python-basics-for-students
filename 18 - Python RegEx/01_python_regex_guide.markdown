# Python RegEx: Beginner-Friendly Teaching Package

This teaching package transforms the provided lesson note on Python Regular Expressions (RegEx) into a structured, beginner-friendly guide. It covers the essentials of the `re` module, key RegEx concepts, and practical applications, ensuring clarity and hands-on learning.

---

## Section 1 — Topical Explanations

### Learning Goals
By the end of this section, you’ll understand:
- What Regular Expressions (RegEx) are and how to use the Python `re` module.
- Key RegEx functions: `findall()`, `search()`, `split()`, and `sub()`.
- Important metacharacters, special sequences, and sets.
- How to work with Match Objects and their properties.

### What is RegEx?
A Regular Expression (RegEx) is a pattern of characters used to search, match, or manipulate text. Think of it like a "search filter" for strings, helping you find specific words, numbers, or patterns. Python’s `re` module provides tools to work with RegEx.

To use RegEx, you first import the `re` module:
```python
import re
```

### Example 1: Basic RegEx with `search()`
Let’s start with a simple example from the lesson note that checks if a string starts with "The" and ends with "Spain".

```python
import re

txt = "The rain in Spain"
x = re.search("^The.*Spain$", txt)

if x:
    print("Match found!")
else:
    print("No match.")
```

**Line-by-Line Explanation**:
- `import re`: Imports the RegEx module.
- `txt = "The rain in Spain"`: Defines the string to search.
- `x = re.search("^The.*Spain$", txt)`:
  - `^The`: Ensures the string starts with "The".
  - `.*`: Matches any characters (except newline) zero or more times (like a wildcard).
  - `Spain$`: Ensures the string ends with "Spain".
  - `re.search()`: Looks for the first match of this pattern in `txt` and returns a Match Object.
- `if x:`: Checks if a match was found (if `x` is not `None`).
- `print("Match found!")`: Outputs if the pattern matches.

**Expected Output**:
```
Match found!
```

**Visual Description**: The code checks the entire string. If it starts with "The" and ends with "Spain" (with any characters in between), it confirms the match. You won’t see the matched text directly unless you print it (we’ll cover this later).

**Common Mistake**:
- Forgetting `^` or `$` might cause the pattern to match substrings. For example, `re.search("The.*Spain", txt)` would match even if "The" isn’t at the start or "Spain" isn’t at the end.
- **Fix**: Always include `^` and `$` when you want to match the entire string.

**Validation Check**: Try changing `txt` to `"The sun in Spain"` or `"Rain in Spain"`. What happens? (Answer: It should match for the first, but not the second.)

### Key RegEx Functions
The `re` module provides four main functions:
1. **findall()**: Returns a list of all matches.
2. **search()**: Returns a Match Object for the first match.
3. **split()**: Splits the string at each match.
4. **sub()**: Replaces matches with specified text.

Let’s explore each with beginner-friendly examples.

#### 1. `findall()`: Finding All Matches
The `findall()` function returns a list of all non-overlapping matches of a pattern.

```python
import re

txt = "The rain in Spain"
x = re.findall("ai", txt)
print(x)
```

**Line-by-Line**:
- `re.findall("ai", txt)`: Searches for all occurrences of "ai" in `txt`.
- `print(x)`: Outputs a list of matches.

**Expected Output**:
```
['ai', 'ai']
```
(The string has "ai" in "rain" and "Spain".)

**Common Mistake**: Expecting `findall()` to return a Match Object. It returns a list, even if empty.
- **Fix**: Check if the list is empty to confirm no matches: `if not x: print("No matches")`.

#### 2. `search()`: Finding the First Match
The `search()` function returns a Match Object for the first match or `None` if no match is found.

```python
import re

txt = "The rain in Spain"
x = re.search("\s", txt)
print("First whitespace at position:", x.start())
```

**Line-by-Line**:
- `re.search("\s", txt)`: Searches for the first whitespace (`\s` matches spaces, tabs, etc.).
- `x.start()`: Returns the starting position of the match (index in the string).
- `print(...)`: Outputs the position.

**Expected Output**:
```
First whitespace at position: 3
```
(The first space is between "The" and "rain".)

**Common Mistake**: Not checking if `x` is `None` before calling `x.start()`.
- **Fix**: Add `if x:` before accessing Match Object properties.

#### 3. `split()`: Splitting Strings
The `split()` function splits the string at each match.

```python
import re

txt = "The rain in Spain"
x = re.split("\s", txt)
print(x)
```

**Line-by-Line**:
- `re.split("\s", txt)`: Splits `txt` at each whitespace.
- `print(x)`: Outputs the resulting list.

**Expected Output**:
```
['The', 'rain', 'in', 'Spain']
```

**Variation with maxsplit**:
```python
x = re.split("\s", txt, 1)
print(x)
```
**Output**:
```
['The', 'rain in Spain']
```
(Only splits at the first whitespace due to `maxsplit=1`.)

**Common Mistake**: Assuming `split()` splits on the entire pattern. It splits at the matched pattern, removing it.
- **Fix**: Test with small examples to confirm the split points.

#### 4. `sub()`: Replacing Matches
The `sub()` function replaces matches with specified text.

```python
import re

txt = "The rain in Spain"
x = re.sub("\s", "9", txt, 2)
print(x)
```

**Line-by-Line**:
- `re.sub("\s", "9", txt, 2)`: Replaces the first two whitespaces with "9".
- `print(x)`: Outputs the modified string.

**Expected Output**:
```
The9rain9in Spain
```

**Common Mistake**: Forgetting the `count` parameter, replacing all matches.
- **Fix**: Specify `count` (e.g., `2`) to limit replacements.

### Metacharacters
Metacharacters give RegEx patterns special powers. Here’s a beginner-friendly breakdown of key ones:
- `[]`: Matches any single character in the set. Example: `[a-m]` matches any lowercase letter from `a` to `m`.
- `\`: Indicates a special sequence or escapes special characters. Example: `\d` matches digits.
- `.`: Matches any character (except newline). Example: `he..o` matches "hello" or "hexxo".
- `^`: Matches the start of a string. Example: `^The`.
- `$`: Matches the end of a string. Example: `Spain$`.
- `*`: Zero or more occurrences. Example: `he.*o` matches "heo", "hello", etc.
- `+`: One or more occurrences. Example: `he.+o` matches "hello" but not "heo".
- `?`: Zero or one occurrence. Example: `he.?o` matches "heo" or "hero".
- `{}`: Exactly the specified number of occurrences. Example: `he.{2}o` matches "hello".
- `|`: Either/or. Example: `falls|stays` matches "falls" or "stays".
- `()`: Groups patterns. Example: `(ab)+` matches "ab", "abab", etc.

**Example with Metacharacters**:
```python
import re

txt = "hello world"
x = re.findall("h.*o", txt)
print(x)
```
**Output**: `['hello']`
(Finds "hello" because `.*` matches any characters between "h" and "o".)

### Special Sequences
Special sequences start with `\` and have specific meanings:
- `\d`: Matches digits (0–9).
- `\D`: Matches non-digits.
- `\s`: Matches whitespace.
- `\S`: Matches non-whitespace.
- `\w`: Matches word characters (a–z, A–Z, 0–9, `_`).
- `\W`: Matches non-word characters.
- `\b`: Matches word boundaries. Example: `r"\bain"` matches "ain" in "rain" but not "pain".
- `\A`: Matches the start of the string.
- `\Z`: Matches the end of the string.

**Example with Special Sequences**:
```python
import re

txt = "The year is 2023!"
x = re.findall(r"\d+", txt)
print(x)
```
**Output**: `['2023']`
(Finds all sequences of digits.)

### Sets
Sets use `[]` to define a range of characters to match:
- `[a-n]`: Matches any lowercase letter from `a` to `n`.
- `[^a-n]`: Matches any character *not* in `a` to `n`.
- `[0-9]`: Matches any digit.
- `[a-zA-Z]`: Matches any letter (uppercase or lowercase).

**Example with Sets**:
```python
import re

txt = "The cat is 3 years old"
x = re.findall("[0-9]", txt)
print(x)
```
**Output**: `['3']`
(Finds single digits.)

### Match Object
A Match Object (returned by `search()`) contains details about a match:
- `.span()`: Returns a tuple of start and end positions.
- `.string`: Returns the original string.
- `.group()`: Returns the matched text.

**Example**:
```python
import re

txt = "The rain in Spain"
x = re.search(r"\bS\w+", txt)
print("Match:", x.group())
print("Position:", x.span())
print("Original string:", x.string)
```

**Output**:
```
Match: Spain
Position: (12, 17)
Original string: The rain in Spain
```

**Common Mistake**: Accessing Match Object methods without checking if the match exists.
- **Fix**: Use `if x:` before calling `x.group()`, `x.span()`, etc.

**Validation Check**: Modify the pattern to `r"\bT\w+"`. What matches? (Answer: "The".)

**One-Line Takeaway**: RegEx helps you search and manipulate text using patterns, with `re` functions like `findall()`, `search()`, `split()`, and `sub()`.

---

## Section 2 — Class Exercise

### Objectives
- Practice using `findall()`, `search()`, and `sub()` with simple RegEx patterns.
- Understand metacharacters and special sequences in real-world scenarios.

### Step-by-Step Instructions
1. **Find All Digits**:
   - Write a program that uses `findall()` to extract all digits from the string `"My phone number is 123-456-7890"`.
   - Print the list of digits.
2. **Check for a Word**:
   - Use `search()` to check if the string `"I love to code"` starts with "I" and contains "code".
   - Print whether a match was found and, if so, its position.
3. **Replace Vowels**:
   - Use `sub()` to replace all vowels (`a`, `e`, `i`, `o`, `u`) in `"Hello World"` with `*`.
   - Print the modified string.

### Hints
- For digits, use the `\d` special sequence.
- For the word check, combine `^` and a pattern for "code".
- For vowels, use a set like `[aeiou]`.

### Checkpoints
- After step 1, check if your list contains `['1', '2', '3', '4', '5', '6', '7', '8', '9', '0']`.
- After step 2, confirm the match starts at position 0.
- After step 3, verify the output is `"H*ll* W*rld"`.

---

## Section 3 — Weekly Project

### Overview
Create a simple **Email Validator** that checks if a user-provided string is a valid email address using RegEx. This project builds on the lesson’s concepts of patterns, sets, and metacharacters.

### Milestones
1. **Basic Pattern Matching**:
   - Write a RegEx pattern to match emails like `user@domain.com`.
   - Use `search()` to check if a string matches the pattern.
2. **User Input**:
   - Prompt the user to enter an email address.
   - Validate it and print whether it’s valid.
3. **Error Reporting**:
   - If invalid, suggest what might be wrong (e.g., missing `@`, no domain).

### Deliverables
- A Python script that:
  - Takes user input.
  - Uses a RegEx pattern to validate the email.
  - Outputs "Valid email" or "Invalid email" with a reason.
- A short comment explaining your RegEx pattern.

### Research Prompts
- What characters are allowed in the local part of an email (before `@`)?
- What are valid domain extensions (e.g., `.com`, `.org`)?
- How can `\w` and `[a-zA-Z0-9]` differ in email validation?

### Assessment Criteria
- **Correctness**: The pattern correctly identifies valid emails (e.g., `name@domain.com`) and rejects invalid ones (e.g., `name@domain`, `name.domain.com`).
- **Clarity**: The code is commented, and the output is user-friendly.
- **Completeness**: The script handles user input and provides feedback.

### Extension Ideas
- Add support for more complex emails (e.g., `name.surname@sub.domain.co.uk`).
- Count how many valid emails are entered in a loop until the user types "quit".

**Sample Pattern Idea** (not a full solution):
- Use `[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}` to match emails.
- Break it down: local part, `@`, domain, and extension.

---

## Completion Checklist
- [ ] Understand the four main `re` functions (`findall`, `search`, `split`, `sub`) and their outputs.
- [ ] Run the example codes and observe their outputs.
- [ ] Identify at least three metacharacters and two special sequences with examples.
- [ ] Complete the class exercise and verify outputs match expected results.
- [ ] Start the weekly project by writing a basic email validation pattern.
- [ ] Avoid common mistakes like accessing Match Object properties without checking for `None`.

**Common Pitfalls**:
- Forgetting to import `re`.
- Using metacharacters without escaping them (e.g., `.` instead of `\.` for a literal dot).
- Not testing patterns with varied inputs to catch edge cases.

**One-Line Takeaway**: Python’s `re` module lets you search and manipulate text with powerful RegEx patterns, making tasks like validation and extraction efficient and flexible.