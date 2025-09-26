# **Python Functions: School Fee Payment Calculator Solution and Explanation**

This markdown provides the complete code solution to the **Weekly Project: School Fee Payment Calculator** from the Python Functions lesson, tailored for Nigerian beginners. It includes the full code, a detailed step-by-step explanation, and connects the solution to relatable Nigerian scenarios, following the instructional framework. The response is structured to be clear, beginner-friendly, and engaging, ensuring students understand the solution and feel proud of creating a practical tool.

---

## **Section 1 – Code Solution**

Below is the complete Python code for the "School Fee Payment Calculator" project, which calculates total school fees based on a student’s class level, extra fees, and an optional discount, using functions, conditionals, and return values.

```python
def calculate_fees(class_level, extra_fees=0, *, discount=0):
    # Define base fees for each class level
    if class_level == "JSS1":
        base_fee = 20000
    elif class_level == "JSS2":
        base_fee = 22000
    elif class_level == "JSS3":
        base_fee = 25000
    elif class_level == "SS1":
        base_fee = 30000
    elif class_level == "SS2":
        base_fee = 32000
    elif class_level == "SS3":
        base_fee = 35000
    else:
        return f"Error: Invalid class level {class_level}. Please use JSS1, JSS2, JSS3, SS1, SS2, or SS3."

    # Calculate total fee
    total_fee = base_fee + extra_fees - discount

    # Return formatted message
    return f"Total fees for {class_level} with ₦{extra_fees} extra and ₦{discount} discount is ₦{total_fee}."

# Test the function with different class levels, extra fees, and discounts
print(calculate_fees("JSS1", 5000))
print(calculate_fees("SS3"))
print(calculate_fees("JSS2", 3000, discount=1000))
print(calculate_fees("SSS1"))  # Invalid class level
```

**Output:**
```
Total fees for JSS1 with ₦5000 extra and ₦0 discount is ₦25000.
Total fees for SS3 with ₦0 extra and ₦0 discount is ₦35000.
Total fees for JSS2 with ₦3000 extra and ₦1000 discount is ₦24000.
Error: Invalid class level SSS1. Please use JSS1, JSS2, JSS3, SS1, SS2, or SS3.
```

---

## **Section 2 – Explanation**

This section explains the code step-by-step, connecting each part to the concepts from the Python Functions lesson (functions, parameters, default parameters, keyword-only arguments, return values, and conditionals) and using Nigerian-themed analogies to make it relatable and confidence-building for beginners.

### **Overview of the Project**
The "School Fee Payment Calculator" project asked students to create a function that calculates total school fees based on a student’s class level (e.g., JSS1, SS3), optional extra fees (e.g., for books or uniforms), and an optional discount (e.g., for early payment). The function uses conditionals to assign base fees, performs calculations, and returns a clear message. This project builds on functions, conditionals (from prior lessons), and string formatting, creating a practical tool that feels like something a school bursar might use.

### **Breaking Down the Code**

**Line 1: Defining the Function**
```python
def calculate_fees(class_level, extra_fees=0, *, discount=0):
```
- **What it does**: Creates a function named `calculate_fees` with three parameters: `class_level` (a string like "JSS1"), `extra_fees` (a number with a default of `0`), and `discount` (a keyword-only argument with a default of `0`).
- **Explanation**: The `def` keyword defines the function, like naming a ledger "School Fee Calculator." The `class_level` parameter is required, `extra_fees=0` sets a default of no extra fees, and `*, discount=0` makes `discount` keyword-only, meaning it must be specified as `discount=value`. This is like a school bursar requiring you to explicitly label any discount (e.g., "Discount = ₦1000") rather than assuming it.
- **Nigerian Context**: This is similar to a school bursar asking for your class level and any extra payments (like for textbooks) while offering a discount for early payment, but only if you clearly state you’re eligible.

**Lines 2-13: Assigning Base Fees with Conditionals**
```python
    if class_level == "JSS1":
        base_fee = 20000
    elif class_level == "JSS2":
        base_fee = 22000
    elif class_level == "JSS3":
        base_fee = 25000
    elif class_level == "SS1":
        base_fee = 30000
    elif class_level == "SS2":
        base_fee = 32000
    elif class_level == "SS3":
        base_fee = 35000
    else:
        return f"Error: Invalid class level {class_level}. Please use JSS1, JSS2, JSS3, SS1, SS2, or SS3."
```
- **What it does**: Uses `if-elif-else` statements to assign a base fee based on the `class_level`. If the input is invalid, it returns an error message.
- **Explanation**: The `if-elif` checks match the `class_level` to predefined values (e.g., `"JSS1"` sets `base_fee = 20000`). If none match, the `else` block returns an error message using an f-string. This ensures the function handles invalid inputs gracefully, like a bursar rejecting a wrong class code on a payment slip.
- **Nigerian Context**: This is like a school cashier checking your class level on a fee schedule to determine what you owe, rejecting entries like "SSS1" because they don’t match the school’s records.

**Line 15: Calculating the Total Fee**
```python
    total_fee = base_fee + extra_fees - discount
```
- **What it does**: Calculates the total fee by adding `base_fee` and `extra_fees`, then subtracting `discount`.
- **Explanation**: This simple arithmetic combines the base fee (set by class level), any extra fees (e.g., for uniforms), and subtracts any discount. For example, for JSS1 with `base_fee=20000`, `extra_fees=5000`, and `discount=0`, the result is `20000 + 5000 - 0 = 25000`. This is stored in the `total_fee` variable.
- **Nigerian Context**: This is like a bursar adding up your school fees, extra charges for books, and subtracting a scholarship discount, giving you the final amount to pay.

**Line 17: Returning the Formatted Message**
```python
    return f"Total fees for {class_level} with ₦{extra_fees} extra and ₦{discount} discount is ₦{total_fee}."
```
- **What it does**: Uses an f-string to create a clear message with the class level, extra fees, discount, and total fee, then returns it.
- **Explanation**: The f-string formats the output to be readable, e.g., `"Total fees for JSS1 with ₦5000 extra and ₦0 discount is ₦25000."`. The `return` statement sends this message back to the caller, allowing it to be printed or used elsewhere. This ensures the function produces a usable result.
- **Nigerian Context**: This is like the bursar handing you a payment receipt that clearly lists your class, extra charges, any discounts, and the total amount, ready to show your parents.

**Lines 19-22: Testing the Function**
```python
print(calculate_fees("JSS1", 5000))
print(calculate_fees("SS3"))
print(calculate_fees("JSS2", 3000, discount=1000))
print(calculate_fees("SSS1"))  # Invalid class level
```
- **What it does**: Calls the `calculate_fees` function with different inputs to test its functionality and prints the results.
- **Explanation**:
  - `calculate_fees("JSS1", 5000)` uses `class_level="JSS1"` (base fee ₦20,000), `extra_fees=5000`, and default `discount=0`, calculating `20000 + 5000 - 0 = 25000` and returning the formatted message.
  - `calculate_fees("SS3")` uses `class_level="SS3"` (base fee ₦35,000), default `extra_fees=0`, and default `discount=0`, calculating `35000 + 0 - 0 = 35000`.
  - `calculate_fees("JSS2", 3000, discount=1000)` uses `class_level="JSS2"` (base fee ₦22,000), `extra_fees=3000`, and `discount=1000` (keyword-only), calculating `22000 + 3000 - 1000 = 24000`.
  - `calculate_fees("SSS1")` triggers the `else` block, returning an error message for an invalid class level.
- **Nigerian Context**: This is like a student testing a payment calculator by entering different class levels and fees, similar to checking a school portal to confirm what they owe for the term.

### **Why It’s Beginner-Friendly**
- **Simplicity**: The code uses basic function concepts (parameters, defaults, keyword-only arguments, return) and conditionals, keeping it accessible for beginners.
- **Relatability**: The school fee theme resonates with Nigerian students, who are familiar with paying fees and seeing breakdowns for things like uniforms or exams.
- **Practicality**: The program feels like a real tool a school might use, making it exciting to build and share.
- **Confidence-Building**: The clear, formatted output shows students they can create something useful with just a few lines, reinforcing their learning.

### **Connection to Previous Concepts**
- **Functions**: Uses `def`, parameters, and `return` from the lesson.
- **Conditionals**: Builds on `if-elif-else` to assign fees, assuming students learned this previously.
- **Variables**: Stores `base_fee` and `total_fee` as variables.
- **String Formatting**: Uses f-strings to create readable messages, building on string concatenation.
- **Printing**: Displays results with `print()`, a familiar concept.

### **Why It’s Fun and Show-Off Worthy**
The program feels like a real-world tool a school bursar might use, making it exciting for students to show off. They can say, “I built a fee calculator for my school!” and share it with friends or family, sparking conversations about their coding skills. The Nigerian school context makes it relatable, and the professional-looking output (like a receipt) adds to the pride factor.

---

This solution and explanation provide a complete, beginner-friendly implementation of the "School Fee Payment Calculator" project, using Python functions and conditionals in a way that’s practical, engaging, and deeply rooted in Nigerian culture. Students can confidently share this program, feeling proud of creating a tool that solves a familiar problem.