# **Instructional Guide for Python Loops**

Below is a structured guide covering the concepts of **while loops** and **for loops**, tailored for complete beginners in Python programming.

---

## **Section 1 – Explanations**

### **While Loops**
A **while loop** in Python repeatedly executes a block of code as long as a specified condition is true. It’s like a repeating task that continues until a certain condition is no longer met. You need to set up a variable (often called an index or counter) and ensure the condition changes during the loop to avoid an infinite loop.

**Example** (Print numbers 1 to 5):
```python
i = 1
while i < 6:
    print(i)
    i += 1
```
- **Explanation**: 
  - `i = 1` sets the starting value of the counter.
  - The condition `i < 6` checks if `i` is less than 6. If true, the loop runs.
  - Inside the loop, `print(i)` outputs the value of `i`, and `i += 1` increments `i` by 1.
  - When `i` becomes 6, the condition `i < 6` is false, and the loop stops.
  - Output: `1`, `2`, `3`, `4`, `5`.

**Key Features of While Loops**:
- **Break Statement**: Stops the loop entirely, even if the condition is still true.
  - Example:
    ```python
    i = 1
    while i < 6:
        print(i)
        if i == 3:
            break
        i += 1
    ```
    - Output: `1`, `2`, `3` (stops when `i` is 3 due to `break`).
- **Continue Statement**: Skips the current iteration and moves to the next one.
  - Example:
    ```python
    i = 0
    while i < 6:
        i += 1
        if i == 3:
            continue
        print(i)
    ```
    - Output: `1`, `2`, `4`, `5`, `6` (skips `3` due to `continue`).
- **Else Statement**: Runs a block of code once the loop condition becomes false (unless stopped by `break`).
  - Example:
    ```python
    i = 1
    while i < 6:
        print(i)
        i += 1
    else:
        print("i is no longer less than 6")
    ```
    - Output: `1`, `2`, `3`, `4`, `5`, `i is no longer less than 6`.

### **For Loops**
A **for loop** is used to iterate over a sequence, such as a list, tuple, string, or range of numbers. It’s ideal for going through each item in a collection without manually managing a counter.

**Example** (Loop through a list of fruits):
```python
fruits = ["apple", "banana", "cherry"]
for x in fruits:
    print(x)
```
- **Explanation**:
  - The loop assigns each item in `fruits` to the variable `x` one at a time.
  - `print(x)` outputs each item.
  - Output: `apple`, `banana`, `cherry`.

**Key Features of For Loops**:
- **Looping Through a String**:
  - Example:
    ```python
    for x in "banana":
        print(x)
    ```
    - Output: `b`, `a`, `n`, `a`, `n`, `a` (each character is printed).
- **Break Statement**: Stops the loop early.
  - Example:
    ```python
    fruits = ["apple", "banana", "cherry"]
    for x in fruits:
        print(x)
        if x == "banana":
            break
    ```
    - Output: `apple`, `banana` (stops after `banana`).
- **Continue Statement**: Skips the current iteration.
  - Example:
    ```python
    fruits = ["apple", "banana", "cherry"]
    for x in fruits:
        if x == "banana":
            continue
        print(x)
    ```
    - Output: `apple`, `cherry` (skips `banana`).
- **Range Function**:
  - `range(start, stop, step)` generates a sequence of numbers.
  - Example:
    ```python
    for x in range(2, 6):
        print(x)
    ```
    - Output: `2`, `3`, `4`, `5` (starts at 2, stops before 6).
  - Example with step:
    ```python
    for x in range(2, 30, 3):
        print(x)
    ```
    - Output: `2`, `5`, `8`, ..., `29` (increments by 3).
- **Else Statement**: Runs when the loop completes normally (not stopped by `break`).
  - Example:
    ```python
    for x in range(6):
        print(x)
    else:
        print("Finally finished!")
    ```
    - Output: `0`, `1`, `2`, `3`, `4`, `5`, `Finally finished!`.
- **Nested Loops**: A loop inside another loop.
  - Example:
    ```python
    adj = ["red", "big", "tasty"]
    fruits = ["apple", "banana", "cherry"]
    for x in adj:
        for y in fruits:
            print(x, y)
    ```
    - Output: Pairs like `red apple`, `red banana`, ..., `tasty cherry`.
- **Pass Statement**: Used as a placeholder to avoid errors in empty loops.
  - Example:
    ```python
    for x in [0, 1, 2]:
        pass
    ```
    - Does nothing but prevents a syntax error.

---

## **Section 2 – Class Exercise**

**Real-World Problem**: Counting Books on a Shelf
You’re organizing a small library and want to count how many books are on a shelf, but you only want to count up to 5 books. If you find a damaged book (say, book number 3), you skip counting it. Use a **while loop** to simulate counting books and skip the damaged one.

**Step-by-Step Guidance**:
1. Initialize a counter variable to represent the book number (start at 1).
2. Use a while loop to keep counting as long as the book number is less than or equal to 5.
3. Inside the loop, check if the book number is 3 (the damaged book). If it is, use `continue` to skip printing it.
4. Print the book number for each valid book and increment the counter.
5. After the loop, print a message saying, “Finished counting books!” using the `else` statement.

**Expected Output**:
```
Book 1
Book 2
Book 4
Book 5
Finished counting books!
```

**Tips**:
- Make sure to increment the counter to avoid an infinite loop.
- Use the `continue` statement to skip book number 3.
- Test your code to ensure it skips book 3 and stops after book 5.

---

## **Section 3 – Weekly Project**

**Real-World Scenario**: Creating a Simple Shopping List Printer
You’re helping a friend organize their grocery shopping. They have a list of items and want to print each item paired with a category (e.g., “Fruit: apple”). They also want to print the position (index) of each item in the list (starting from 1). Use a **for loop** to iterate through the items and a **nested loop** or **range()** to handle the categories and indexing. If the item is “milk,” skip it because it’s already been bought.

**Project Brief**:
- Create a program that:
  1. Defines a list of grocery items (e.g., `["apple", "milk", "bread", "banana"]`).
  2. Defines a list of categories (e.g., `["Fruit", "Dairy", "Bakery"]`).
  3. Uses a for loop to iterate through the grocery items.
  4. For each item, prints its position (e.g., “Item 1”) and pairs it with a category (e.g., “Fruit: apple”).
  5. Skips the item “milk” using the `continue` statement.
  6. After the loop, prints “Grocery list complete!” using the `else` statement.
- **Challenge**: Experiment with how you assign categories to items (e.g., all items could be “Fruit” for simplicity, or try matching categories creatively).
- **Curiosity Spark**: Can you think of a way to stop the loop early if you reach a specific item (hint: this uses the `break` statement, which you’ve learned)?

**Step-by-Step Guidelines**:
1. Create a list of at least 4 grocery items, including “milk.”
2. Create a list of at least 2 categories.
3. Use a for loop with `range()` to iterate through the grocery list and track the index (to print “Item 1,” “Item 2,” etc.).
4. Inside the loop, check if the item is “milk.” If it is, use `continue` to skip it.
5. For each item, print its index (add 1 to the `range()` index to start at 1) and pair it with a category (you can assign the same category or cycle through the category list).
6. Use the `else` statement to print a completion message after the loop finishes.
7. Test your program to ensure “milk” is skipped and the output is clear.

**Example Output** (for reference, not the solution):
```
Item 1: Fruit: apple
Item 3: Bakery: bread
Item 4: Fruit: banana
Grocery list complete!
```

**Tips**:
- Use the `range(len(grocery_list))` to iterate through the list with indices.
- Be creative with how you assign categories (e.g., manually or using a loop).
- Test the `continue` statement to ensure “milk” is skipped.
- If you want to explore, try adding a `break` if a certain item is reached to see how it affects the `else` block.