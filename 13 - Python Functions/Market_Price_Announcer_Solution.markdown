# **Python Functions: Market Price Announcer Solution and Explanation**

This markdown provides the code solution to the **Class Exercise: Market Price Announcer** from the previous Python Functions lesson, tailored for Nigerian beginners. It includes the complete code, a detailed explanation of each part, and ties it to relatable Nigerian scenarios, following the instructional framework. The response is structured to be clear, beginner-friendly, and engaging, ensuring students understand the solution and feel proud of the practical outcome.

---

## **Section 1 – Code Solution**

Below is the complete Python code for the "Market Price Announcer" exercise, which creates a function to announce the price of market items in a friendly, Nigerian market trader style.

```python
def announce_price(item, price=100):
    message = f"Fresh {item} costs ₦{price} only!"
    return message

# Test the function with different items and prices
print(announce_price("Tomatoes", 500))
print(announce_price("Yam", 1200))
print(announce_price("Fish", 2000))
print(announce_price("Pepper"))  # Uses default price
```

**Output:**
```
Fresh Tomatoes costs ₦500 only!
Fresh Yam costs ₦1200 only!
Fresh Fish costs ₦2000 only!
Fresh Pepper costs ₦100 only!
```

---

## **Section 2 – Explanation**

This section explains the code step-by-step, connecting each part to the concepts from the Python Functions lesson and using Nigerian-themed analogies to make it relatable and confidence-building for beginners.

### **Overview of the Exercise**
The "Market Price Announcer" exercise asked students to create a function that takes an item name and its price, then returns a friendly message like a market trader calling out to customers. The function should be versatile, handle multiple items, and include a default price for cases when no price is provided. This uses **functions**, **parameters**, **default parameters**, and **return values** from the lesson note.

### **Breaking Down the Code**

**Line 1: Defining the Function**
```python
def announce_price(item, price=100):
```
- **What it does**: Creates a function named `announce_price` with two parameters: `item` (the product name, like "Tomatoes") and `price` (the cost in Naira, with a default value of `100`).
- **Explanation**: The `def` keyword defines the function, like naming a recipe "Announce Market Price." The `item` parameter is required, while `price=100` means if no price is provided, it defaults to ₦100. This is like a trader assuming a small *sachet of pepper* costs ₦100 unless told otherwise.
- **Nigerian Context**: Think of a trader in Mile 12 Market shouting prices. If you don’t specify the price of an item, they might assume a standard price for something small, like *shombo*.

**Line 2: Creating the Message**
```python
    message = f"Fresh {item} costs ₦{price} only!"
```
- **What it does**: Uses an f-string to combine the `item` and `price` into a friendly message, stored in the variable `message`.
- **Explanation**: The f-string `f"Fresh {item} costs ₦{price} only!"` inserts the values of `item` and `price` into the text. For example, if `item="Tomatoes"` and `price=500`, it creates the string `"Fresh Tomatoes costs ₦500 only!"`. This is a concise way to format strings, making the output lively and engaging.
- **Nigerian Context**: This mimics how traders call out to attract customers, like “Fresh ugu costs ₦200 only!” It’s exciting and makes the program feel like a real market interaction.

**Line 3: Returning the Message**
```python
    return message
```
- **What it does**: Sends the `message` back to where the function was called, allowing it to be used (e.g., printed or stored).
- **Explanation**: The `return` statement is like a trader handing you a receipt after shouting the price. It ensures the function produces a result that can be used elsewhere in the program. Without `return`, the function would create the message but not share it.
- **Nigerian Context**: Imagine a trader shouting the price, then writing it on a piece of paper for you to take home—that’s what `return` does.

**Lines 5-8: Testing the Function**
```python
print(announce_price("Tomatoes", 500))
print(announce_price("Yam", 1200))
print(announce_price("Fish", 2000))
print(announce_price("Pepper"))  # Uses default price
```
- **What it does**: Calls the `announce_price` function with different arguments and prints the returned messages.
- **Explanation**:
  - `announce_price("Tomatoes", 500)` passes `"Tomatoes"` as `item` and `500` as `price`, returning `"Fresh Tomatoes costs ₦500 only!"`, which `print` displays.
  - Similarly, `"Yam", 1200` and `"Fish", 2000` produce their respective messages.
  - `announce_price("Pepper")` omits the `price`, so it uses the default `100`, returning `"Fresh Pepper costs ₦100 only!"`.
  - This tests the function’s flexibility, showing it works with both specified and default prices.
- **Nigerian Context**: This is like walking through Oyingbo Market, hearing traders announce prices for different items. The default price is like a trader assuming a standard price for a small item if you don’t ask for a specific one.

### **Why It’s Beginner-Friendly**
- **Simplicity**: The code uses basic concepts (functions, parameters, return) without complex logic, perfect for beginners.
- **Relatability**: The market theme connects to everyday Nigerian experiences, like bargaining in a local market, making it fun to learn.
- **Practicality**: The output feels like something students can show off, saying, “I built a program that shouts market prices like a trader!”
- **Confidence-Building**: Each function call produces a clear, useful result, showing students they can create real-world tools with just a few lines of code.

### **Connection to Previous Concepts**
- **Variables**: The `message` variable stores the formatted string, building on variable lessons.
- **Printing**: The `print()` function displays the output, a familiar concept from earlier lessons.
- **String Concatenation**: The f-string combines strings and variables, reinforcing string manipulation.

### **Why It’s Fun and Show-Off Worthy**
The program mimics the vibrant energy of a Nigerian market, making it exciting to run and share. Students can imagine showing their friends a program that “talks” like a trader in Computer Village or Balogun Market, sparking conversations like, “See the market announcer I coded!”

---

This solution and explanation provide a complete, beginner-friendly implementation of the "Market Price Announcer" exercise, using Python functions in a way that’s practical, engaging, and deeply rooted in Nigerian culture. Students can proudly share this program, feeling confident in their growing Python skills.