# **Solution to the “Market Shopping List Counter” Exercise**

This markdown file provides the complete Python code solution for the **Market Shopping List Counter** exercise from the lesson on **while loops** and **for loops**, along with a detailed explanation. The exercise is designed to reinforce loop concepts using a Nigerian-themed scenario, ensuring it’s relatable and beginner-friendly.

---

## **Section 1 – Code Solution**

Below is the Python code that implements the “Market Shopping List Counter” exercise. The program uses a **for loop** to print items from a market shopping list (skipping “yam”) and a **while loop** to count customers (stopping at 3).

```python
# Market Shopping List Counter

# Part 1: For loop to print shopping list, skipping "yam"
market_list = ["rice", "beans", "yam", "fish", "oil"]
print("Items on your shopping list:")
for item in market_list:
    if item == "yam":
        continue
    print(item)

# Part 2: While loop to count customers, stopping at 3
customers = 1
print("\nCounting customers in the queue:")
while customers <= 5:
    if customers == 3:
        break
    print(f"Customer {customers}")
    customers += 1
else:
    print("Market shopping done!")
```

**Output**:
```
Items on your shopping list:
rice
beans
fish
oil

Counting customers in the queue:
Customer 1
Customer 2
```

---

## **Section 2 – Explanation**

This section explains the code step-by-step, connecting it to Nigerian experiences and ensuring clarity for beginners. The explanation follows the **AI Instructional Framework for Teaching Python Beginners (Nigeria-Focused Edition)**, focusing on the concepts used in the exercise: **for loops**, **while loops**, **continue**, **break**, and **else**.

### **Line-by-Line Breakdown**

#### **Part 1: For Loop with Continue**
```python
market_list = ["rice", "beans", "yam", "fish", "oil"]
```
- **Purpose**: Creates a list called `market_list` containing common items you might buy at a Nigerian market, like Oyingbo or Balogun Market.
- **Relatable Example**: This is like writing a shopping list on a piece of paper before heading to the market to buy ingredients for jollof rice.

```python
print("Items on your shopping list:")
```
- **Purpose**: Prints a header to make the output clear, like announcing to your family what you’re buying today.

```python
for item in market_list:
    if item == "yam":
        continue
    print(item)
```
- **Line 1: `for item in market_list:`** – Iterates over each item in `market_list`. The variable `item` takes the value of each list element (e.g., `"rice"`, then `"beans"`, etc.), one at a time.
  - **Relatable Example**: It’s like checking each item on your market list as you pick them from a stall.
- **Line 2: `if item == "yam":`** – Checks if the current item is `"yam"`.
- **Line 3: `continue`** – Skips the rest of the loop (the `print(item)` statement) when the item is `"yam"`, moving to the next item. This represents skipping yam because it’s too expensive today.
  - **Relatable Example**: You see yam at the market but decide to skip it because the price is too high (maybe ₦2000 for a tuber!).
- **Line 4: `print(item)`** – Prints each item that isn’t skipped.
- **Output**: `rice`, `beans`, `fish`, `oil` (one per line). `"yam"` is skipped due to `continue`.

#### **Part 2: While Loop with Break and Else**
```python
customers = 1
```
- **Purpose**: Initializes a variable `customers` to 1, representing the first customer in a queue at your market stall.
- **Relatable Example**: You’re a trader counting customers waiting to buy your goods, like airtime or small chops.

```python
print("\nCounting customers in the queue:")
```
- **Purpose**: Prints a header with a newline (`\n`) to separate it from the previous output, making it clear we’re now counting customers.

```python
while customers <= 5:
    if customers == 3:
        break
    print(f"Customer {customers}")
    customers += 1
else:
    print("Market shopping done!")
```
- **Line 1: `while customers <= 5:`** – The loop runs as long as `customers` is less than or equal to 5, representing up to 5 customers in the queue.
  - **Relatable Example**: You’re serving customers one by one until you’ve served 5 or decide to stop early.
- **Line 2: `if customers == 3:`** – Checks if `customers` equals 3.
- **Line 3: `break`** – Stops the loop immediately when `customers` is 3, even though the condition `customers <= 5` is still true.
  - **Relatable Example**: You stop serving customers after the third one because the market is closing early (maybe it’s 6 PM).
- **Line 4: `print(f"Customer {customers}")`** – Prints the current customer number using an f-string for a clean format (e.g., `Customer 1`).
- **Line 5: `customers += 1`** – Increments `customers` by 1 to move to the next customer. Without this, the loop would run forever, like waiting endlessly for more customers.
- **Line 6: `else:`** – The `else` block runs only if the loop finishes naturally (i.e., when `customers <= 5` becomes false).
- **Line 7: `print("Market shopping done!")`** – Prints a message when the loop ends naturally. In this case, it *won’t* run because the loop stops early with `break`.
- **Output**: `Customer 1`, `Customer 2`. The loop stops at 3 due to `break`, so the `else` block doesn’t execute.

### **Why It Works**
- The **for loop** iterates over the shopping list, skipping “yam” to mimic a real-world decision to avoid an expensive item.
- The **while loop** counts customers but stops early at 3, simulating a situation like a market closing or a trader taking a break.
- The `continue` statement ensures only desired items are printed, and the `break` statement controls when the customer counting stops.
- The `else` statement is included to show what happens when the loop ends naturally, though it’s not triggered here due to `break`.

### **Relatable Nigerian Context**
This program feels like managing a small market stall in Nigeria. You’re checking off items from your shopping list (skipping expensive ones like yam) and serving a queue of customers until the market closes. It’s practical and something you can proudly show to friends, saying, “I built a program to track my market business!”

---

## **Section 3 – Notes for Beginners**
- **Confidence-Building**: This exercise uses simple loops to create something useful, like managing a market stall. You can start with small steps (printing a list, counting numbers) and build a tool you can share with peers.
- **Common Mistake**: Forgetting to increment `customers` in the while loop would cause an infinite loop, like waiting forever for customers. Always check your loop conditions!
- **Next Steps**: Try modifying the code to:
  - Add more items to the list and skip multiple items (e.g., skip both “yam” and “oil”).
  - Change the `break` condition to stop at a different customer number.
  - Print a custom message in the `else` block if all customers are served.

This solution aligns with the **Pride Factor Rule**, giving you a program that’s fun, relatable, and worth boasting about in a Nigerian context!