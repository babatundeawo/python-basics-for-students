# **Solution to Class Exercise: Counting Books on a Shelf**

This document provides the solution to the class exercise from the Python loops lesson, specifically the **Counting Books on a Shelf** problem. The exercise requires using a **while loop** to count up to 5 books, skipping book number 3 (a damaged book) using the `continue` statement, and printing a completion message using the `else` statement. Below is the solution with an explanation tailored for complete beginners.

---

## **Explanation**

The goal is to simulate counting books on a shelf, from book 1 to book 5, while skipping book 3 (the damaged book). We use a **while loop** because we need to control the loop with a condition (counting up to 5) and handle skipping a specific book. Here’s how the solution works:

1. **Initialize the Counter**: We start with a variable `book_number` set to 1, representing the first book.
2. **Set Up the While Loop**: The loop runs as long as `book_number` is less than or equal to 5 (i.e., we count up to book 5).
3. **Check for the Damaged Book**: Inside the loop, we check if `book_number` is 3. If it is, we use the `continue` statement to skip the rest of the loop body and move to the next iteration.
4. **Print Valid Books**: For all other books, we print a message like “Book 1” to indicate we’re counting that book.
5. **Increment the Counter**: We increment `book_number` by 1 in each iteration to avoid an infinite loop.
6. **Completion Message**: After the loop ends (when `book_number` exceeds 5), the `else` block prints “Finished counting books!”.

**Key Concepts Used**:
- **While Loop**: Repeats the code block while `book_number <= 5` is true.
- **Continue Statement**: Skips printing when `book_number` is 3.
- **Else Statement**: Runs when the loop condition becomes false, indicating the counting is complete.
- **Incrementing**: Ensures the loop progresses by increasing `book_number`.

**Expected Output**:
```
Book 1
Book 2
Book 4
Book 5
Finished counting books!
```

---

## **Solution Code**

```python
book_number = 1
while book_number <= 5:
    if book_number == 3:
        book_number += 1
        continue
    print(f"Book {book_number}")
    book_number += 1
else:
    print("Finished counting books!")
```

---

## **Step-by-Step Walkthrough**

1. **Initialization**:
   - `book_number = 1`: Sets the starting book number to 1.
2. **Loop Condition**:
   - `while book_number <= 5`: The loop runs as long as `book_number` is less than or equal to 5.
3. **Check for Damaged Book**:
   - `if book_number == 3`: Checks if the current book is the damaged one (book 3).
   - `book_number += 1`: Increments the counter *before* the `continue` statement to avoid an infinite loop (if we skip incrementing, `book_number` stays 3 forever).
   - `continue`: Skips the rest of the loop body (i.e., the `print` statement) for book 3.
4. **Print Valid Books**:
   - `print(f"Book {book_number}")`: Prints the book number in a formatted string (e.g., “Book 1”) for all books except book 3.
5. **Increment Counter**:
   - `book_number += 1`: Increments the counter for the next iteration (skipped for book 3 since it’s handled in the `if` block).
6. **Else Block**:
   - `else: print("Finished counting books!")`: Runs when the loop condition (`book_number <= 5`) becomes false, indicating the counting is done.

---

## **Why This Works**

- The `continue` statement ensures book 3 is skipped, so it’s not printed.
- Incrementing `book_number` in both the `if` block (for book 3) and the main loop body ensures the loop progresses and terminates after book 5.
- The `else` statement provides a clear end to the counting process, reinforcing the loop’s completion.
- The code is simple and beginner-friendly, using only a single counter and basic control flow statements (`while`, `if`, `continue`, `else`).

This solution directly addresses the exercise’s requirements and uses only the concepts from the **while loop** section of the lesson, making it accessible for complete beginners.