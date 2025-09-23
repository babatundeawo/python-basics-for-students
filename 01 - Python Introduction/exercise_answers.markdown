# Answers to Class Exercise: Create and Run Your First Python Program

**Objective**: Write a Python program that prints your name to the screen.

**Guidelines and Answers**:

1. **Open a text editor** (e.g., Notepad on Windows, TextEdit on Mac, or any code editor like VS Code).  
   - *Answer*: Any text editor will work. For example, you can use Notepad (Windows) or TextEdit (Mac) set to plain text mode, or a dedicated editor like Thonny for simplicity.

2. **Write a Python command to print your name**. Hint: Use the `print()` function and place your name inside quotation marks.  
   - *Answer*: For example, if your name is "Alex," you would write:  
     ```python
     print("Alex")
     ```

3. **Save the file as `myname.py`** in a folder you can easily find.  
   - *Answer*: Save the file with the exact name `myname.py` (ensure the `.py` extension is included). For example, save it in a folder like `C:\Users\YourName\Documents\Python` on Windows or `~/Documents/Python` on Linux/Mac.

4. **Open your command line or terminal** and navigate to the folder:  
   - On Windows: Use Command Prompt and navigate with `cd path/to/folder`.  
   - On Linux/Mac: Use Terminal and navigate similarly.  
   - *Answer*: For example, if the file is in `C:\Users\YourName\Documents\Python`, open Command Prompt and type:  
     ```
     cd C:\Users\YourName\Documents\Python
     ```  
     On Linux/Mac, for `~/Documents/Python`, type:  
     ```
     cd ~/Documents/Python
     ```

5. **Run the program** by typing `python myname.py` and pressing Enter.  
   - *Answer*: In the command line or terminal, type:  
     ```
     python myname.py
     ```  
     This executes the Python file.

6. **Check the output**. It should display your name.  
   - *Answer*: If your code is `print("Alex")`, the output will be:  
     ```
     Alex
     ```

7. **If you encounter errors**, ensure your file is saved correctly with the `.py` extension and that Python is installed.  
   - *Answer*: Common issues include:  
     - Forgetting the `.py` extension when saving (e.g., saving as `myname` instead of `myname.py`).  
     - Python not installed: Check by running `python --version`. If not installed, download from [https://www.python.org/](https://www.python.org/).  
     - Incorrect directory: Ensure you’re in the correct folder using `cd` before running `python myname.py`.

**Expected Outcome**: The program should print your name to the screen. For example, if your name is Alex, the output will be:  
```
Alex
```