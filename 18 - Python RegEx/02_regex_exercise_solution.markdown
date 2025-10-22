# Python RegEx Class Exercise: Solutions and Explanations

This Markdown file provides the solutions to the class exercise from the Python RegEx teaching package, along with detailed explanations. The exercise focuses on using `findall()`, `search()`, and `sub()` with simple RegEx patterns to build practical skills for beginners. Each solution includes a line-by-line explanation, expected output, visual description, common mistakes, and validation checks, adhering to the beginner-friendly instructional framework.

---

## Exercise Objectives
- Practice using `findall()`, `search()`, and `sub()` with simple RegEx patterns.
- Understand metacharacters and special sequences in real-world scenarios.

## Exercise Tasks
1. **Find All Digits**: Extract all digits from the string `"My phone number is 123-456-7890"` using `findall()` and print the list.
2. **Check for a Word**: Use `search()` to check if the string `"I love to code"` starts with "I" and contains "code". Print whether a match was found and its position.
3. **Replace Vowels**: Use `sub()` to replace all vowels (`a`, `e`, `i`, `o`, `u`) in `"Hello World"` with `*`. Print the modified string.

---

## Solutions and Explanations

### Task 1: Find All Digits
**Objective**: Extract all digits from `"My phone number is 123-456-7890"` using `findall()`.

**Solution**:
```python
import re

txt = "My phone number is 123-456-7890"
digits = re.findall(r"\d", txt)
print(digits)
```

**Line-by-Line Explanation**:
- `import re`: Imports the RegEx module to use its functions.
- `txt = "My phone number is 123-456-7890"`: Defines the input string containing a phone number.
- `digits = re.findall(r"\d", txt)`:
  - `\d`: A special sequence that matches any digit (0–9).
  - `r"..."`: Uses a raw string to ensure backslashes are treated literally.
  - `re.findall()`: Returns a list of all matches of the pattern in `txt`.
- `print(digits)`: Outputs the list of all digits found.

**Expected Output**:
```
['1', '2', '3', '4', '5', '6', '7', '8', '9', '0']
```

**Visual Description**: The output is a list of single-digit strings, representing each digit in the phone number. The hyphens and other characters are ignored because the pattern `\d` only matches digits.

**Common Mistake**:
- Using `\D` instead of `\d`, which matches non-digits (e.g., letters, spaces, hyphens).
- **Fix**: Double-check the special sequence: `\d` for digits, `\D` for non-digits.

**Validation Check**: The output should contain exactly 10 digits in the order they appear: `['1', '2', '3', '4', '5', '6', '7', '8', '9', '0']`. Try changing the string to `"123 456"` and verify you get `['1', '2', '3', '4', '5', '6']`.

### Task 2: Check for a Word
**Objective**: Use `search()` to check if `"I love to code"` starts with "I" and contains "code". Print whether a match was found and its position.

**Solution**:
```python
import re

txt = "I love to code"
x = re.search(r"^I.*code", txt)
if x:
    print("Match found at position:", x.start())
else:
    print("No match found.")
```

**Line-by-Line Explanation**:
- `import re`: Imports the RegEx module.
- `txt = "I love to code"`: Defines the input string.
- `x = re.search(r"^I.*code", txt)`:
  - `^I`: Ensures the string starts with "I".
  - `.*`: Matches any characters (except newline) zero or more times.
  - `code`: Matches the literal string "code".
  - `re.search()`: Returns a Match Object for the first match or `None` if no match.
- `if x:`: Checks if a match was found.
- `print("Match found at position:", x.start())`: Outputs the starting position of the match (index 0 since `^I` anchors at the start).
- `else: print("No match found.")`: Handles the case where no match is found.

**Expected Output**:
```
Match found at position: 0
```

**Visual Description**: The code checks if the string starts with "I" and includes "code" anywhere after. Since `"I love to code"` satisfies both conditions, it matches, and the starting position (0) is printed.

**Common Mistake**:
- Omitting `^`, which could allow matches where "I" isn’t at the start (e.g., `"HI love to code"`).
- **Fix**: Always include `^` when the pattern must start at the beginning of the string.

**Validation Check**: Test with `"HI love to code"` (should fail) and `"I code"` (should match at position 0). The pattern ensures "I" is at the start and "code" appears somewhere.

### Task 3: Replace Vowels
**Objective**: Replace all vowels (`a`, `e`, `i`, `o`, `u`) in `"Hello World"` with `*` using `sub()`.

**Solution**:
```python
import re

txt = "Hello World"
result = re.sub(r"[aeiou]", "*", txt, flags=re.IGNORECASE)
print(result)
```

**Line-by-Line Explanation**:
- `import re`: Imports the RegEx module.
- `txt = "Hello World"`: Defines the input string.
- `result = re.sub(r"[aeiou]", "*", txt, flags=re.IGNORECASE)`:
  - `[aeiou]`: A set that matches any single vowel (`a`, `e`, `i`, `o`, `u`).
  - `*`: The replacement string for each matched vowel.
  - `flags=re.IGNORECASE`: Makes the pattern case-insensitive, so it matches both lowercase and uppercase vowels (e.g., `E` in "Hello").
  - `re.sub()`: Replaces all matches of the pattern with `*`.
- `print(result)`: Outputs the modified string.

**Expected Output**:
```
H*ll* W*rld
```

**Visual Description**: The output string has all vowels (`e`, `o`) replaced with `*`. Non-vowel characters remain unchanged. The `re.IGNORECASE` flag ensures `E` in "Hello" is also replaced.

**Common Mistake**:
- Forgetting `flags=re.IGNORECASE`, which would miss uppercase vowels like `E`.
- **Fix**: Include `re.IGNORECASE` when case-insensitive matching is needed.

**Validation Check**: Verify the output is `"H*ll* W*rld"`. Try changing the input to `"HELLO"` and confirm you get `"H*LL*"`.

---

## Completion Checklist
- [ ] Ran the solution for Task 1 and verified the output is `['1', '2', '3', '4', '5', '6', '7', '8', '9', '0']`.
- [ ] Ran the solution for Task 2 and confirmed the match starts at position 0.
- [ ] Ran the solution for Task 3 and verified the output is `"H*ll* W*rld"`.
- [ ] Tested each solution with different inputs to ensure robustness.
- [ ] Understood the role of `\d`, `^`, `.*`, and `[aeiou]` in the patterns.

**Common Pitfalls**:
- Not using raw strings (`r"..."`) for patterns, which can cause backslash issues.
- Forgetting to check for `None` in `search()` before accessing Match Object methods.
- Omitting `flags=re.IGNORECASE` when matching both uppercase and lowercase characters.

**One-Line Takeaway**: The `findall()`, `search()`, and `sub()` functions, combined with patterns like `\d` and `[aeiou]`, enable powerful text processing in Python.