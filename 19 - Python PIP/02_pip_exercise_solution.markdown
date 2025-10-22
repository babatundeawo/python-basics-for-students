# Python PIP Class Exercise: Solutions and Explanations

This Markdown file provides the solutions to the class exercise from the Python PIP teaching package, along with detailed explanations. The exercise focuses on using PIP commands to install, use, and remove the `requests` package, and verifying the results. Each solution includes step-by-step instructions, expected outputs, visual descriptions, common mistakes, and validation checks, adhering to the beginner-friendly instructional framework.

---

## Exercise Objectives
- Practice using PIP commands to install, use, and remove a package.
- Understand how to verify package installation and explore PyPI.

## Exercise Tasks
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

---

## Solutions and Explanations

### Task 1: Check PIP Version
**Objective**: Confirm PIP is installed and note its version.

**Solution** (run in command line):
```bash
pip --version
```

**Explanation**:
- **Command**: `pip --version` checks the installed version of PIP.
- **Where to Run**: Open a command line (e.g., Command Prompt on Windows, Terminal on macOS/Linux). If PIP is in your system’s PATH, you can run it from any directory. Otherwise, navigate to Python’s `Scripts` directory (e.g., `C:\Users\YourName\AppData\Local\Programs\Python\Python36-32\Scripts`).
- **What It Does**: Displays the PIP version and its installation path.

**Expected Output** (example):
```
pip 18.1 from c:\users\YourName\appdata\local\programs\python\python36-32\lib\site-packages\pip (python 3.6)
```

**Visual Description**: The output shows the PIP version (e.g., `18.1`) and the path to its installation, confirming PIP is ready to use. If PIP isn’t installed, you’ll see an error like `'pip' is not recognized`.

**Common Mistake**:
- Running the command without PIP in the system PATH or in the wrong directory.
- **Fix**: Ensure Python and PIP are added to your PATH during Python installation, or navigate to the `Scripts` directory. Alternatively, use `python -m pip --version` to run PIP via Python.

**Validation Check**: Verify you see a version number. If not, install PIP by downloading `get-pip.py` from [https://pypi.org/project/pip/](https://pypi.org/project/pip/) and running `python get-pip.py`.

### Task 2: Install a Package
**Objective**: Install the `requests` package and verify its installation.

**Solution** (run in command line):
```bash
pip install requests
pip list
```

**Explanation**:
- **Command 1**: `pip install requests` downloads and installs the `requests` package from PyPI ([https://pypi.org/](https://pypi.org/)).
- **Command 2**: `pip list` displays all installed packages to confirm `requests` is included.
- **Process**: PIP fetches the latest version of `requests` and installs it into Python’s `site-packages` directory.

**Expected Output** (example for `pip install requests`):
```
Collecting requests
  Downloading requests-2.32.3-py3-none-any.whl (64 kB)
     |████████████████ personally | 64 kB 2.0 MB/s
Installing collected packages: requests
Successfully installed requests-2.32.3
```

**Expected Output** (example for `pip list`, partial output):
```
Package         Version
--------------- -------
pip             18.1
requests        2.32.3
setuptools      39.0.1
...
```

**Visual Description**: The `pip install` command shows a progress bar for downloading and confirms successful installation. The `pip list` command displays a table where `requests` appears with its version (e.g., `2.32.3`).

**Common Mistake**:
- Misspelling the package name (e.g., `request` instead of `requests`).
- **Fix**: Check the exact package name on [https://pypi.org/](https://pypi.org/). For `requests`, use `pip install requests`.

**Validation Check**: After installation, confirm `requests` appears in the `pip list` output. If it doesn’t, ensure you’re using the correct Python environment (e.g., `python3 -m pip list` for Python 3).

### Task 3: Use the Package
**Objective**: Write a Python script to fetch the status code of `https://api.github.com` using the `requests` package.

**Solution**:
```python
import requests

url = "https://api.github.com"
response = requests.get(url)
print("Status code:", response.status_code)
```

**Line-by-Line Explanation**:
- `import requests`: Imports the `requests` package, which simplifies HTTP requests.
- `url = "https://api.github.com"`: Defines the URL to fetch (GitHub’s API endpoint).
- `response = requests.get(url)`: Sends an HTTP GET request to the URL and stores the response.
- `print("Status code:", response.status_code)`: Outputs the HTTP status code (e.g., 200 for success, 404 for not found).

**Expected Output**:
```
Status code: 200
```

**Visual Description**: The script outputs a single line with the status code of the HTTP request. A status code of 200 indicates the request was successful, meaning the URL is accessible.

**Common Mistake**:
- Running the script without installing `requests`, causing a `ModuleNotFoundError`.
- **Fix**: Ensure `pip install requests` was run successfully before executing the script.

**Validation Check**: Verify the output is `Status code: 200`. Try a different URL (e.g., `https://api.github.com/nonexistent`) and confirm you get a different status code (e.g., 404).

### Task 4: Remove the Package
**Objective**: Uninstall the `requests` package and verify its removal.

**Solution** (run in command line):
```bash
pip uninstall requests
pip list
```

**Explanation**:
- **Command 1**: `pip uninstall requests` removes the `requests` package.
- **Prompt**: PIP asks for confirmation (e.g., `Proceed (y/n)?`). Type `y` to proceed.
- **Command 2**: `pip list` confirms `requests` is no longer installed.
- **Process**: PIP deletes the package files from the `site-packages` directory.

**Expected Output** (example for `pip uninstall requests`):
```
Uninstalling requests-2.32.3:
  Would remove:
    c:\users\YourName\appdata\local\programs\python\python36-32\lib\site-packages\requests-2.32.3-py3.6.egg-info
    c:\users\YourName\appdata\local\programs\python\python36-32\lib\site-packages\requests\*
Proceed (y/n)? y
Successfully uninstalled requests-2.32.3
```

**Expected Output** (example for `pip list`, partial output):
```
Package         Version
--------------- -------
pip             18.1
setuptools      39.0.1
...
```

**Visual Description**: The `pip uninstall` command lists the files to be removed and waits for confirmation. After typing `y`, it confirms the uninstallation. The `pip list` output no longer includes `requests`.

**Common Mistake**:
- Typing `n` at the uninstall prompt, leaving the package installed.
- **Fix**: Ensure you type `y` to confirm uninstallation.

**Validation Check**: Confirm `requests` is absent from the `pip list` output after uninstalling. If it still appears, verify you’re using the correct Python environment.

---

## Completion Checklist
- [ ] Ran `pip --version` and confirmed a version number (e.g., `18.1`).
- [ ] Installed `requests` and verified it appears in `pip list`.
- [ ] Ran the Python script and confirmed the status code is 200 for `https://api.github.com`.
- [ ] Uninstalled `requests` and verified it’s no longer in `pip list`.
- [ ] Tested with an incorrect URL or package name to understand error handling.

**Common Pitfalls**:
- Not adding PIP to the system PATH, causing `'pip' is not recognized` errors.
- Using the wrong Python environment (e.g., installing in Python 2 but running in Python 3).
- Forgetting to confirm the uninstallation prompt with `y`.

**One-Line Takeaway**: PIP commands (`install`, `list`, `uninstall`) and the `requests` package enable you to manage and use external libraries to enhance Python projects, like fetching web data.