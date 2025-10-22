# Python Try Except Weekly Project: File Reader Tool Solution and Explanation

This Markdown file provides the solution to the weekly project from the Python Try Except teaching package, which involves creating a **File Reader Tool** that reads a user-specified text file, counts its lines, and handles errors gracefully. The solution includes a complete, beginner-friendly Python script that uses `try`, `except`, `else`, `finally`, and `raise` to manage file operations and validate inputs. The explanations adhere to the instructional framework, ensuring clarity and hands-on learning for beginners.

---

## Project Overview
The goal is to create a Python script that:
- Prompts the user for a file name (e.g., `data.txt`).
- Validates the input is not empty, raising a `ValueError` if it is.
- Reads the file, counts its lines, and handles errors like `FileNotFoundError` and `PermissionError`.
- Ensures the file is closed using `finally`.
- Provides clear feedback and a completion message.

---

## Solution

Below is the complete Python script for the File Reader Tool.

```python
def read_file_lines(filename):
    """
    Reads a file and counts its lines, handling errors with try-except.
    Args:
        filename (str): Name of the file to read.
    Returns:
        tuple: (success (bool), message (str), line_count (int or None)).
    """
    if not filename.strip():
        raise ValueError("File name cannot be empty")

    file = None
    line_count = None
    try:
        file = open(filename, 'r')
        lines = file.readlines()
        line_count = len(lines)
        return True, f"Successfully read {filename}. It has {line_count} lines.", line_count
    except FileNotFoundError:
        return False, f"Error: File '{filename}' not found", None
    except PermissionError:
        return False, f"Error: Permission denied when accessing '{filename}'", None
    except Exception as e:
        return False, f"Unexpected error: {str(e)}", None
    finally:
        if file is not None:
            file.close()
        print("File operation completed")

def main():
    """Main function to run the File Reader Tool."""
    print("Welcome to the File Reader Tool!")
    print("Enter a text file name to count its lines (or 'quit' to exit).")
    
    while True:
        filename = input("\nEnter file name: ").strip()
        
        if filename.lower() == "quit":
            print("Exiting File Reader Tool.")
            break
        
        try:
            success, message, line_count = read_file_lines(filename)
            print(message)
        except ValueError as e:
            print(f"Error: {e}")
            print("File operation completed")

if __name__ == "__main__":
    main()
```

---

## Explanation

### Learning Goals
- Understand how to use `try`, `except`, `else`, and `finally` for file operations.
- Raise custom exceptions (`ValueError`) for input validation.
- Handle specific file-related exceptions (`FileNotFoundError`, `PermissionError`).
- Ensure resource cleanup with `finally`.

### Code Breakdown
Here’s a detailed explanation of the script, designed for beginners.

#### Function: `read_file_lines`
```python
def read_file_lines(filename):
    if not filename.strip():
        raise ValueError("File name cannot be empty")
    file = None
    line_count = None
    try:
        file = open(filename, 'r')
        lines = file.readlines()
        line_count = len(lines)
        return True, f"Successfully read {filename}. It has {line_count} lines.", line_count
    except FileNotFoundError:
        return False, f"Error: File '{filename}' not found", None
    except PermissionError:
        return False, f"Error: Permission denied when accessing '{filename}'", None
    except Exception as e:
        return False, f"Unexpected error: {str(e)}", None
    finally:
        if file is not None:
            file.close()
        print("File operation completed")
```
- **Purpose**: Reads a file, counts its lines, and handles errors.
- **Key Code**:
  - `if not filename.strip(): raise ValueError(...)`: Validates the input, raising a `ValueError` if empty.
  - `file = None`: Initializes `file` to avoid errors in `finally` if opening fails.
  - `try:`: Attempts to open and read the file.
  - `file = open(filename, 'r')`: Opens the file in read mode.
  - `lines = file.readlines()`: Reads all lines into a list.
  - `line_count = len(lines)`: Counts the lines.
  - `return True, ...`: Returns success status, a message, and the line count.
  - `except FileNotFoundError:`: Catches when the file doesn’t exist.
  - `except PermissionError:`: Catches when access is denied.
  - `except Exception as e:`: Catches unexpected errors (e.g., `IOError`).
  - `finally:`: Ensures the file is closed if opened and prints a completion message.
- **Why `file = None`?**: Prevents errors in `finally` if `open()` fails before assigning `file`.

**Common Mistake**: Not closing the file, causing resource leaks.
- **Fix**: Use `finally` or a `with` statement (though `finally` is used here to meet project requirements).

#### Main Function
```python
def main():
    print("Welcome to the File Reader Tool!")
    print("Enter a text file name to count its lines (or 'quit' to exit).")
    while True:
        filename = input("\nEnter file name: ").strip()
        if filename.lower() == "quit":
            print("Exiting File Reader Tool.")
            break
        try:
            success, message, line_count = read_file_lines(filename)
            print(message)
        except ValueError as e:
            print(f"Error: {e}")
            print("File operation completed")
```
- **Purpose**: Manages user interaction in a loop.
- **Key Code**:
  - `print(...)`: Displays instructions.
  - `filename = input(...).strip()`: Gets and cleans user input.
  - `if filename.lower() == "quit"`: Exits on "quit".
  - `try:`: Wraps the call to `read_file_lines` to catch `ValueError`.
  - `success, message, line_count = read_file_lines(filename)`: Calls the function to process the file.
  - `except ValueError as e:`: Catches empty input errors.
  - `print("File operation completed")`: Ensures consistency with `finally` message in `read_file_lines`.

**Expected Output** (example interaction):
```
Welcome to the File Reader Tool!
Enter a text file name to count its lines (or 'quit' to exit).

Enter file name: data.txt
Successfully read data.txt. It has 3 lines.
File operation completed

Enter file name: nonexistent.txt
Error: File 'nonexistent.txt' not found
File operation completed

Enter file name: 
Error: File name cannot be empty
File operation completed

Enter file name: quit
Exiting File Reader Tool.
```

**Visual Description**: The script prompts for a file name, processes it, and displays the line count or an error message. The `finally` block ensures a completion message after each attempt, and the loop allows multiple tries until "quit".

**Common Mistake**: Not handling empty input, causing unexpected behavior.
- **Fix**: Validate input with `raise ValueError` and catch it in `main`.

**Validation Checks**:
- Create a `data.txt` with 3 lines, test, and confirm the output shows 3 lines.
- Test with a nonexistent file (e.g., `nonexistent.txt`) and verify the `FileNotFoundError` message.
- Test with an empty input (`""`) and confirm the `ValueError` message.
- Test with a read-only file you don’t have permission to access (if possible) to verify `PermissionError`.

---

## Assessment Criteria
- **Correctness**: The script reads files, counts lines, and handles `FileNotFoundError`, `PermissionError`, and empty inputs correctly.
- **Clarity**: Code is commented, and messages are user-friendly (e.g., “File ‘nonexistent.txt’ not found”).
- **Completeness**: Validates input, handles multiple exceptions, and ensures file closure with `finally`.

**Common Pitfalls**:
- Forgetting to initialize `file = None`, causing errors in `finally`.
- Using a bare `except` instead of specific exceptions, masking issues.
- Not closing the file, risking resource leaks.

---

## Extension Ideas
- **Word Count**: Add a feature to count words using `sum(len(line.split()) for line in lines)`.
- **Multiple Files**: Allow multiple file inputs in the loop until "quit".
- **File Type Check**: Reject non-text files by checking extensions (e.g., `.txt`).

---

## Completion Checklist
- [ ] The script validates empty input with `ValueError`.
- [ ] Handles `FileNotFoundError` and `PermissionError` with specific messages.
- [ ] Counts lines correctly and closes files in `finally`.
- [ ] Tested with valid, nonexistent, and empty file names.
- [ ] Includes a completion message in all cases.
- [ ] Avoids bare `except` and ensures specific exception handling.

**One-Line Takeaway**: The File Reader Tool uses `try-except`, `else`, `finally`, and `raise` to safely read files, count lines, and handle errors, ensuring robust file operations.