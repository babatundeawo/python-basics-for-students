# Python PIP: Beginner-Friendly Teaching Package

This teaching package transforms the provided lesson note on Python PIP into a structured, beginner-friendly guide. It covers the essentials of PIP, the package manager for Python, including how to install, use, manage, and troubleshoot packages. The goal is to make the concept accessible while guiding learners toward practical mastery through hands-on exercises and a project.

---

## Section 1 — Topical Explanations

### Learning Goals
By the end of this section, you’ll understand:
- What PIP is and its role as Python’s package manager.
- How to check if PIP is installed and its version.
- How to install, use, remove, and list Python packages.
- Common commands and their practical applications.

### What is PIP?
PIP (Pip Installs Packages) is Python’s package manager, a tool that helps you install, manage, and remove Python libraries (called packages or modules). Think of PIP as a librarian who fetches books (packages) from a library (like PyPI, the Python Package Index) to enhance your Python projects. If you have Python 3.4 or later, PIP is included by default.

### What is a Package?
A package is a collection of Python files (modules) that provide reusable code for your projects. For example, the `camelcase` package converts text to camelCase format, saving you from writing that functionality yourself.

### Checking if PIP is Installed
To verify if PIP is installed and check its version, you use the command line.

**Example Code** (run in your command line):
```bash
pip --version
```

**Explanation**:
- `pip`: The command to invoke the PIP tool.
- `--version`: Displays the installed PIP version.
- **Where to run it**: Open your command line (e.g., Command Prompt on Windows, Terminal on macOS/Linux) and navigate to Python’s `Scripts` directory (e.g., `C:\Users\YourName\AppData\Local\Programs\Python\Python36-32\Scripts` on Windows). However, if PIP is in your system’s PATH, you can run it from any directory.

**Expected Output** (example):
```
pip 18.1 from c:\users\YourName\appdata\local\programs\python\python36-32\lib\site-packages\pip (python 3.6)
```

**Visual Description**: The command outputs the PIP version and its installation path. If PIP is not installed, you’ll see an error like `'pip' is not recognized`.

**Common Mistake**:
- Running the command in the wrong directory or without PIP in the system PATH.
- **Fix**: Ensure Python and PIP are added to your PATH during Python installation, or navigate to the `Scripts` directory.

**Validation Check**: Run `pip --version`. If you see a version number, PIP is installed. If not, follow the installation instructions below.

### Installing PIP
If PIP is not installed (e.g., for older Python versions), download it from [https://pypi.org/project/pip/](https://pypi.org/project/pip/) and follow the installation instructions there. Typically, this involves downloading `get-pip.py` and running:
```bash
python get-pip.py
```

### Downloading and Installing a Package
PIP makes installing packages easy. Let’s install the `camelcase` package as shown in the lesson note.

**Example Code** (run in command line):
```bash
pip install camelcase
```

**Explanation**:
- `pip install`: The command to download and install a package.
- `camelcase`: The name of the package to install from PyPI.
- **Process**: PIP downloads the package from [https://pypi.org/](https://pypi.org/) and installs it into Python’s `site-packages` directory.

**Expected Output** (example):
```
Collecting camelcase
  Downloading camelcase-0.2-py3-none-any.whl (3.1 kB)
Installing collected packages: camelcase
Successfully installed camelcase-0.2
```

**Visual Description**: The command line shows PIP downloading and installing the package, confirming success when complete.

**Common Mistake**:
- Running `pip install` without an internet connection or with a typo in the package name (e.g., `camelCase` instead of `camelcase`).
- **Fix**: Ensure you’re online and use the exact package name from PyPI.

**Validation Check**: After installation, run `pip list` to confirm `camelcase` appears in the list of installed packages.

### Using a Package
Once installed, you can import and use the package in your Python code.

**Example Code** (in a Python script):
```python
import camelcase

c = camelcase.CamelCase()
txt = "hello world"
print(c.hump(txt))
```

**Line-by-Line Explanation**:
- `import camelcase`: Imports the `camelcase` package.
- `c = camelcase.CamelCase()`: Creates an instance of the `CamelCase` class from the package.
- `txt = "hello world"`: Defines a string to process.
- `c.hump(txt)`: Calls the `hump` method to convert the string to camelCase (capitalizing the first letter of each word and removing spaces).
- `print(c.hump(txt))`: Outputs the result.

**Expected Output**:
```
HelloWorld
```

**Visual Description**: The output is a camelCase string where each word’s first letter is capitalized, and spaces are removed (e.g., "hello world" becomes "HelloWorld").

**Common Mistake**:
- Forgetting to install the package before importing it, resulting in a `ModuleNotFoundError`.
- **Fix**: Run `pip install camelcase` first.

**Validation Check**: Change the input to `"my name is python"` and verify the output is `MyNameIsPython`.

### Finding Packages
You can browse packages on [https://pypi.org/](https://pypi.org/), which hosts thousands of Python packages. Search for packages by name or functionality (e.g., "data analysis" for packages like `pandas`).

### Removing a Package
To remove a package, use the `uninstall` command.

**Example Code** (run in command line):
```bash
pip uninstall camelcase
```

**Explanation**:
- `pip uninstall`: Removes the specified package.
- `camelcase`: The package to remove.
- **Prompt**: PIP asks for confirmation (e.g., `Proceed (y/n)?`). Type `y` to confirm.

**Expected Output** (example):
```
Uninstalling camelcase-0.2:
  Would remove:
    c:\users\YourName\appdata\local\programs\python\python36-32\lib\site-packages\camelcase-0.2-py3.6.egg-info
    c:\users\YourName\appdata\local\programs\python\python36-32\lib\site-packages\camelcase\*
Proceed (y/n)? y
Successfully uninstalled camelcase-0.2
```

**Visual Description**: PIP lists the files to be removed and waits for your confirmation. After typing `y`, the package is removed.

**Common Mistake**:
- Typing `n` or interrupting the process, leaving the package installed.
- **Fix**: Ensure you confirm with `y`.

**Validation Check**: Run `pip list` after uninstalling to confirm `camelcase` is no longer listed.

### Listing Installed Packages
To see all installed packages, use the `list` command.

**Example Code** (run in command line):
```bash
pip list
```

**Explanation**:
- `pip list`: Displays all packages installed in your Python environment, along with their versions.

**Expected Output** (example):
```
Package         Version
--------------- -------
camelcase       0.2
mysql-connector 2.1.6
pip             18.1
pymongo         3.6.1
setuptools      39.0.1
```

**Visual Description**: The output is a table listing package names and their versions. It helps you confirm what’s installed.

**Common Mistake**:
- Assuming `pip list` shows packages for all Python versions on your system.
- **Fix**: Ensure you’re using the correct Python environment (e.g., run `pip list` with the `pip` tied to your desired Python version).

**Validation Check**: Install a new package (e.g., `pip install requests`) and run `pip list` to see it appear.

**One-Line Takeaway**: PIP simplifies managing Python packages by installing, using, removing, and listing libraries from PyPI.

---

## Section 2 — Class Exercise

### Objectives
- Practice using PIP commands to install, use, and remove a package.
- Understand how to verify package installation and explore PyPI.

### Step-by-Step Instructions
1. **Check PIP Version**:
   - Run `pip --version` in your command line.
   - Note the version and confirm PIP is installed.
2. **Install a Package**:
   - Install the `requests` package using `pip install requests`.
   - Verify it’s installed by running `pip list`.
3. **Use the Package**:
   - Write a Python script that uses the `requests` package to fetch the status code of a website (e.g., `https://api.github.com`).
   - Print the status code (e.g., 200 for success).
4. **Remove the Package**:
   - Uninstall `requests` using `pip uninstall requests` and confirm with `y`.
   - Verify it’s removed using `pip list`.

### Hints
- For step 1, if `pip` isn’t recognized, check your PATH or navigate to Python’s `Scripts` directory.
- For step 3, use `requests.get()` to make a simple HTTP request.
- For step 4, ensure you confirm the uninstallation prompt.

### Checkpoints
- After step 1, confirm you see a version number (e.g., `pip 18.1`).
- After step 2, check that `requests` appears in `pip list`.
- After step 3, verify the status code is 200 for a valid URL.
- After step 4, ensure `requests` is no longer in `pip list`.

**Sample Code for Step 3** (not a full solution):
```python
import requests
response = requests.get("https://api.github.com")
print(response.status_code)
```

---

## Section 3 — Weekly Project

### Overview
Create a **Package Explorer Tool** that allows users to install a package, use it, and display information about installed packages. This project builds on PIP commands and Python scripting.

### Milestones
1. **Package Installation**:
   - Prompt the user to enter a package name to install.
   - Use PIP to install it programmatically.
2. **Package Usage**:
   - Demonstrate the package’s functionality (e.g., for `requests`, fetch a URL’s status code).
   - Handle cases where the package doesn’t exist or fails to install.
3. **Package Information**:
   - List all installed packages and highlight the newly installed one.
   - Allow the user to uninstall the package.

### Deliverables
- A Python script that:
  - Takes a package name as input.
  - Installs the package using PIP.
  - Demonstrates a simple use case (e.g., for `requests`, fetch a URL).
  - Lists all installed packages.
  - Offers to uninstall the package.
- Comments explaining the code and any limitations.

### Research Prompts
- How can you run PIP commands from within a Python script?
- What are common reasons a `pip install` might fail (e.g., network issues, invalid package name)?
- How can you check a package’s version programmatically?

### Assessment Criteria
- **Correctness**: The script installs, uses, and lists packages correctly.
- **Clarity**: The code is commented, and user prompts are clear.
- **Completeness**: The script handles errors (e.g., invalid package names) and provides feedback.

### Extension Ideas
- Add a feature to search PyPI for packages (e.g., using `requests` to query `https://pypi.org`).
- Allow installing specific package versions (e.g., `pip install requests==2.28.1`).
- Save a list of installed packages to a file.

**Sample Approach** (not a full solution):
- Use `subprocess.run(["pip", "install", package_name])` to install packages from Python.
- Check the return code to handle installation errors.

---

## Completion Checklist
- [ ] Understand PIP’s role as a package manager and its key commands (`install`, `uninstall`, `list`).
- [ ] Run the example commands (`pip --version`, `pip install camelcase`, etc.) and verify outputs.
- [ ] Complete the class exercise, confirming each step’s output (e.g., status code 200, package list).
- [ ] Start the weekly project by writing a script to install and use a package like `requests`.
- [ ] Avoid common mistakes like running commands without PIP in PATH or forgetting to confirm uninstallation.

**Common Pitfalls**:
- Not checking if PIP is in the system PATH, causing command errors.
- Installing packages in the wrong Python environment (e.g., Python 2 vs. 3).
- Forgetting to import a package before using it in a script.

**One-Line Takeaway**: PIP simplifies Python development by managing packages, allowing you to install, use, and remove libraries like `camelcase` or `requests` with ease.