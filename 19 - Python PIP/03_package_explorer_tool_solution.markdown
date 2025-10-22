# Python PIP Weekly Project: Package Explorer Tool Solution and Explanation

This Markdown file provides the solution to the weekly project from the Python PIP teaching package, which involves creating a **Package Explorer Tool** using Python and PIP. The tool allows users to install a package, demonstrate its functionality, list installed packages, and optionally uninstall the package. The solution includes a complete, beginner-friendly script with detailed explanations, adhering to the instructional framework for clarity and hands-on learning.

---

## Project Overview
The goal is to create a Python script that:
- Prompts the user to enter a package name to install.
- Installs the package using PIP programmatically.
- Demonstrates the package’s functionality (with a fallback for unknown packages).
- Lists all installed packages, highlighting the new one.
- Offers to uninstall the package.
- Includes comments explaining the code and limitations.

---

## Solution

Below is the complete Python script for the Package Explorer Tool.

```python
import subprocess
import sys
import pkg_resources
import importlib

def run_pip_command(command):
    """
    Runs a PIP command and returns the result.
    Args:
        command (list): List of command arguments (e.g., ["pip", "install", "requests"]).
    Returns:
        tuple: (success (bool), output/error message (str)).
    """
    try:
        result = subprocess.run(
            command,
            capture_output=True,
            text=True,
            check=True
        )
        return True, result.stdout
    except subprocess.CalledProcessError as e:
        return False, f"Error: {e.stderr}"

def install_package(package_name):
    """Installs a package using PIP."""
    print(f"Installing {package_name}...")
    success, message = run_pip_command([sys.executable, "-m", "pip", "install", package_name])
    print(message)
    return success

def demonstrate_package(package_name):
    """
    Demonstrates the package's functionality.
    For 'requests', fetches a URL's status code. Otherwise, shows basic import.
    """
    try:
        module = importlib.import_module(package_name)
        print(f"Successfully imported {package_name}")
        
        # Special case for 'requests' package
        if package_name == "requests":
            response = module.get("https://api.github.com")
            print(f"Status code for https://api.github.com: {response.status_code}")
        else:
            # Generic demonstration: show module's __version__ if available
            version = getattr(module, "__version__", "Unknown")
            print(f"{package_name} version: {version}")
    except ImportError:
        print(f"Failed to import {package_name}. Ensure it's installed correctly.")
    except Exception as e:
        print(f"Error demonstrating {package_name}: {str(e)}")

def list_packages(highlight_package):
    """Lists all installed packages, highlighting the specified package."""
    print("\nInstalled Packages:")
    installed_packages = {pkg.key: pkg.version for pkg in pkg_resources.working_set}
    for pkg, version in sorted(installed_packages.items()):
        marker = " (newly installed)" if pkg == highlight_package.lower() else ""
        print(f"{pkg}: {version}{marker}")

def uninstall_package(package_name):
    """Uninstalls a package using PIP."""
    print(f"\nUninstalling {package_name}...")
    success, message = run_pip_command([sys.executable, "-m", "pip", "uninstall", package_name, "-y"])
    print(message)
    return success

def main():
    """Main function to run the Package Explorer Tool."""
    print("Welcome to the Package Explorer Tool!")
    print("Enter a package name to install and explore (or 'quit' to exit).")
    
    while True:
        package_name = input("\nEnter package name: ").strip()
        
        if package_name.lower() == "quit":
            print("Exiting Package Explorer Tool.")
            break
        
        if not package_name:
            print("Please enter a valid package name.")
            continue
        
        # Install the package
        if install_package(package_name):
            # Demonstrate the package
            print(f"\nDemonstrating {package_name}:")
            demonstrate_package(package_name)
            
            # List all packages
            list_packages(package_name)
            
            # Offer to uninstall
            uninstall_choice = input(f"\nDo you want to uninstall {package_name}? (y/n): ").strip().lower()
            if uninstall_choice == "y":
                uninstall_package(package_name)
                list_packages(package_name)  # Show updated package list
        else:
            print(f"Failed to install {package_name}. Check the package name or your internet connection.")

if __name__ == "__main__":
    main()
```

---

## Explanation

### Learning Goals
- Understand how to run PIP commands programmatically using `subprocess`.
- Use `pkg_resources` to list installed packages.
- Handle package imports dynamically with `importlib`.
- Provide user-friendly feedback and error handling.

### Code Breakdown
Here’s a detailed explanation of the script, focusing on clarity for beginners.

#### Function: `run_pip_command`
```python
def run_pip_command(command):
    try:
        result = subprocess.run(
            command,
            capture_output=True,
            text=True,
            check=True
        )
        return True, result.stdout
    except subprocess.CalledProcessError as e:
        return False, f"Error: {e.stderr}"
```
- **Purpose**: Runs a PIP command (e.g., `pip install requests`) and captures its output.
- **Key Parameters**:
  - `command`: A list of command arguments (e.g., `["pip", "install", "requests"]`).
  - `capture_output=True`: Captures the command’s output.
  - `text=True`: Returns output as strings.
  - `check=True`: Raises an error if the command fails.
- **Returns**: A tuple `(success, message)` where `success` is a boolean and `message` is the command output or error.
- **Why `subprocess`?**: Allows running command-line PIP commands from within Python.

**Common Mistake**: Not handling command failures, leading to uncaught exceptions.
- **Fix**: Use try-except to capture and report errors.

#### Function: `install_package`
```python
def install_package(package_name):
    print(f"Installing {package_name}...")
    success, message = run_pip_command([sys.executable, "-m", "pip", "install", package_name])
    print(message)
    return success
```
- **Purpose**: Installs the specified package using PIP.
- **Key Code**: Uses `sys.executable` to ensure the correct Python environment (e.g., `python -m pip install requests`).
- **Output**: Prints the PIP command’s output (success or error message).
- **Returns**: `True` if installation succeeds, `False` otherwise.

**Common Mistake**: Using `pip` directly instead of `sys.executable -m pip`, which may target the wrong Python environment.
- **Fix**: Always use `sys.executable` for environment consistency.

#### Function: `demonstrate_package`
```python
def demonstrate_package(package_name):
    try:
        module = importlib.import_module(package_name)
        print(f"Successfully imported {package_name}")
        if package_name == "requests":
            response = module.get("https://api.github.com")
            print(f"Status code for https://api.github.com: {response.status_code}")
        else:
            version = getattr(module, "__version__", "Unknown")
            print(f"{package_name} version: {version}")
    except ImportError:
        print(f"Failed to import {package_name}. Ensure it's installed correctly.")
    except Exception as e:
        print(f"Error demonstrating {package_name}: {str(e)}")
```
- **Purpose**: Demonstrates the package’s functionality.
- **Key Code**:
  - `importlib.import_module(package_name)`: Dynamically imports the package to avoid hardcoding.
  - Special case for `requests`: Fetches the status code of `https://api.github.com`.
  - Generic case: Displays the package’s `__version__` attribute (if available).
- **Error Handling**: Catches `ImportError` (if the package isn’t installed) and other exceptions.

**Common Mistake**: Assuming all packages have a `__version__` attribute or specific methods.
- **Fix**: Use `getattr` with a default value and handle specific packages like `requests` separately.

#### Function: `list_packages`
```python
def list_packages(highlight_package):
    print("\nInstalled Packages:")
    installed_packages = {pkg.key: pkg.version for pkg in pkg_resources.working_set}
    for pkg, version in sorted(installed_packages.items()):
        marker = " (newly installed)" if pkg == highlight_package.lower() else ""
        print(f"{pkg}: {version}{marker}")
```
- **Purpose**: Lists all installed packages, highlighting the newly installed one.
- **Key Code**:
  - `pkg_resources.working_set`: Provides a list of installed packages and their versions.
  - `highlight_package`: Marks the new package with “(newly installed)”.
- **Output**: A sorted list of package names and versions.

**Common Mistake**: Not sorting the package list, making it hard to read.
- **Fix**: Use `sorted()` for consistent output.

#### Function: `uninstall_package`
```python
def uninstall_package(package_name):
    print(f"\nUninstalling {package_name}...")
    success, message = run_pip_command([sys.executable, "-m", "pip", "uninstall", package_name, "-y"])
    print(message)
    return success
```
- **Purpose**: Uninstalls the specified package.
- **Key Code**: Uses `-y` to auto-confirm uninstallation, avoiding user prompts in the script.
- **Output**: Prints the PIP command’s output.

**Common Mistake**: Not using `-y`, causing the script to hang waiting for user input.
- **Fix**: Include `-y` for non-interactive uninstallation.

#### Main Function
```python
def main():
    print("Welcome to the Package Explorer Tool!")
    print("Enter a package name to install and explore (or 'quit' to exit).")
    while True:
        package_name = input("\nEnter package name: ").strip()
        if package_name.lower() == "quit":
            print("Exiting Package Explorer Tool.")
            break
        if not package_name:
            print("Please enter a valid package name.")
            continue
        if install_package(package_name):
            print(f"\nDemonstrating {package_name}:")
            demonstrate_package(package_name)
            list_packages(package_name)
            uninstall_choice = input(f"\nDo you want to uninstall {package_name}? (y/n): ").strip().lower()
            if uninstall_choice == "y":
                uninstall_package(package_name)
                list_packages(package_name)
        else:
            print(f"Failed to install {package_name}. Check the package name or your internet connection.")
```
- **Purpose**: Orchestrates the tool’s workflow.
- **Key Code**:
  - Prompts for a package name.
  - Installs, demonstrates, and lists packages.
  - Offers to uninstall and shows the updated package list.
  - Exits on “quit” input.
- **Error Handling**: Checks for empty input and installation failures.

**Expected Output** (example interaction):
```
Welcome to the Package Explorer Tool!
Enter a package name to install and explore (or 'quit' to exit).

Enter package name: requests
Installing requests...
Collecting requests
  Downloading requests-2.32.3-py3-none-any.whl (64 kB)
Installing collected packages: requests
Successfully installed requests-2.32.3

Demonstrating requests:
Successfully imported requests
Status code for https://api.github.com: 200

Installed Packages:
pip: 18.1
requests: 2.32.3 (newly installed)
setuptools: 39.0.1

Do you want to uninstall requests? (y/n): y
Uninstalling requests...
Successfully uninstalled requests-2.32.3

Installed Packages:
pip: 18.1
setuptools: 39.0.1

Enter package name: quit
Exiting Package Explorer Tool.
```

**Visual Description**: The script guides the user through installing a package, showing its functionality, listing packages, and optionally uninstalling. Outputs are clear, with success/error messages and a sorted package list.

**Common Mistake**: Not handling invalid package names or network issues.
- **Fix**: Check the PIP command’s return status and provide user-friendly error messages.

**Validation Checks**:
- Test with `requests` and verify the status code is 200.
- Test with an invalid package name (e.g., `nonexistent-package`) and confirm an error message.
- Test uninstallation and verify the package is removed from the list.

---

## Assessment Criteria
- **Correctness**: The script installs, demonstrates, lists, and uninstalls packages correctly.
- **Clarity**: Code is commented, and user prompts are clear and intuitive.
- **Completeness**: Handles errors (e.g., invalid package names, import failures) and provides feedback.

**Common Pitfalls**:
- Running PIP commands without `sys.executable`, targeting the wrong Python environment.
- Not handling dynamic imports for unknown packages.
- Forgetting to check for empty or invalid user input.

---

## Extension Ideas
- **PyPI Search**: Use `requests` to query `https://pypi.org` for package information.
- **Version Specification**: Allow installing specific versions (e.g., `pip install requests==2.28.1`).
- **Save Package List**: Write the package list to a file using `open()` and `write()`.

---

## Completion Checklist
- [ ] The script installs a package using `subprocess` and `sys.executable`.
- [ ] Demonstrates package functionality (e.g., HTTP request for `requests`).
- [ ] Lists packages with `pkg_resources`, highlighting the new package.
- [ ] Offers to uninstall and updates the package list.
- [ ] Tested with valid (e.g., `requests`) and invalid package names.
- [ ] Includes error handling for installation and import failures.

**One-Line Takeaway**: The Package Explorer Tool uses PIP and Python to install, demonstrate, list, and uninstall packages, providing a user-friendly interface for exploring Python libraries.