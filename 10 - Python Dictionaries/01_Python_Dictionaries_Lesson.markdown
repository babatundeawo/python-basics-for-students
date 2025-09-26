# **AI Instructional Framework for Teaching Python Beginners (Nigeria-Focused Edition)**

Below is a comprehensive response to the lesson note on Python Dictionaries, tailored to the Nigeria-focused instructional framework for beginners. The response is structured into **three sections**: Explanations, Class Exercise, and Weekly Project, adhering to the rules of being clear, relatable, beginner-friendly, and Nigerian-themed while ensuring students feel proud of their work.

---

## **Section 1 – Explanations**

This section explains the concepts in the provided lesson note on Python dictionaries, breaking them down step-by-step with clear language, Nigerian-themed examples, and detailed explanations of all code snippets. The focus is on dictionaries, their properties, methods, and operations, as outlined in the note.

### **What is a Dictionary?**
A dictionary in Python is like a **market stall inventory list** where each item (key) is paired with its details (value). For example, in a Nigerian market, you might have a list where "Yam" is linked to its price, like ₦500. Dictionaries store data in **key:value pairs**, written inside curly brackets `{}`. They are:
- **Ordered** (as of Python 3.7): Items stay in the order you add them, like a queue at a bus park.
- **Changeable**: You can update, add, or remove items, like adjusting the price of goods in a shop.
- **No duplicates**: You can’t have two items with the same key (e.g., two "Yam" entries); the latest one overwrites the earlier one.

**Example from the Lesson Note:**
```python
thisdict = {
  "brand": "Ford",
  "model": "Mustang",
  "year": 1964
}
print(thisdict)
```

**Line-by-Line Explanation:**
- `thisdict = { ... }`: Creates a dictionary called `thisdict` with three key:value pairs. Think of it as a car dealer’s record in Lagos, where each car has details like brand, model, and year.
- `"brand": "Ford"`: The key `"brand"` is paired with the value `"Ford"`. The key is like a label, and the value is the information.
- `"model": "Mustang"`: Another key:value pair, where `"model"` is the key and `"Mustang"` is the value.
- `"year": 1964`: The key `"year"` is paired with the number `1964`.
- `print(thisdict)`: Outputs the entire dictionary, e.g., `{'brand': 'Ford', 'model': 'Mustang', 'year': 1964}`. This is like showing the full car record to a customer.

**Relatable Analogy**: Imagine a school register where each student’s name (key) is linked to their details (value), like class or age. You can quickly find a student’s info by their name without checking the whole list.

### **Dictionary Items**
Dictionary items are the key:value pairs, like `"brand": "Ford"`. You can access a value using its key, like checking the price of an item in a shop.

**Example from the Lesson Note:**
```python
print(thisdict["brand"])
```

**Explanation:**
- `thisdict["brand"]`: Retrieves the value for the key `"brand"`, which is `"Ford"`. It’s like asking a shopkeeper, “What’s the price of rice?” and they check their list.
- Output: `Ford`.

**Nigerian Example**:
```python
market = {
    "item": "Rice",
    "price": 2500,
    "quantity": 10
}
print(market["item"])  # Output: Rice
```
This is like asking, “What item is in stock?” and getting “Rice” as the answer.

### **Ordered or Unordered?**
Since Python 3.7, dictionaries are **ordered**, meaning items stay in the order they were added. In older versions (3.6 or earlier), they were unordered, like a pile of market goods with no fixed arrangement. For beginners, just know that the order you write your dictionary is the order it keeps.

### **Changeable**
You can change dictionary items, like updating the price of an item when the market price changes.

**Example from the Lesson Note:**
```python
thisdict["year"] = 2018
```

**Explanation:**
- `thisdict["year"] = 2018`: Changes the value of the key `"year"` from `1964` to `2018`. It’s like updating a car’s record when it’s refurbished.
- The dictionary becomes `{'brand': 'Ford', 'model': 'Mustang', 'year': 2018}`.

**Nigerian Example**:
```python
market = {
    "item": "Rice",
    "price": 2500
}
market["price"] = 3000
print(market)  # Output: {'item': 'Rice', 'price': 3000}
```

### **No Duplicates**
Dictionaries don’t allow duplicate keys. If you add a key that already exists, the new value overwrites the old one.

**Example from the Lesson Note:**
```python
thisdict = {
  "brand": "Ford",
  "model": "Mustang",
  "year": 1964,
  "year": 2020
}
print(thisdict)
```

**Explanation:**
- The key `"year"` appears twice. The last value (`2020`) overwrites the earlier one (`1964`).
- Output: `{'brand': 'Ford', 'model': 'Mustang', 'year': 2020}`.
- It’s like updating a student’s age in a school register; you keep only the latest information.

### **Dictionary Length**
Use `len()` to count the number of key:value pairs.

**Example from the Lesson Note:**
```python
print(len(thisdict))
```

**Explanation:**
- `len(thisdict)`: Returns the number of key:value pairs, e.g., `3` for `{'brand': 'Ford', 'model': 'Mustang', 'year': 1964}`.
- It’s like counting how many items are listed in a shop’s inventory.

### **Data Types in Dictionaries**
Values in a dictionary can be any data type: strings, numbers, booleans, or even lists.

**Example from the Lesson Note:**
```python
thisdict = {
  "brand": "Ford",
  "electric": False,
  "year": 1964,
  "colors": ["red", "white", "blue"]
}
```

**Explanation:**
- `"brand": "Ford"`: String value.
- `"electric": False`: Boolean value (True/False).
- `"year": 1964`: Integer value.
- `"colors": ["red", "white", "blue"]`: List value.
- It’s like a market record listing an item’s name (string), availability (boolean), price (number), and available sizes (list).

### **The `type()` Function**
Dictionaries are objects of type `dict`.

**Example from the Lesson Note:**
```python
print(type(thisdict))
```

**Explanation:**
- `type(thisdict)`: Returns `<class 'dict'>`, confirming `thisdict` is a dictionary.
- It’s like checking the category of an item in a shop (e.g., “Is this a food item or a clothing item?”).

### **The `dict()` Constructor**
You can create a dictionary using the `dict()` function.

**Example from the Lesson Note:**
```python
thisdict = dict(name="John", age=36, country="Norway")
print(thisdict)
```

**Explanation:**
- `dict(name="John", age=36, country="Norway")`: Creates a dictionary `{'name': 'John', 'age': 36, 'country': 'Norway'}`.
- Uses `=` instead of `:` for key:value pairs, and no curly brackets.
- It’s like writing a quick student profile for a JAMB registration form.

### **Accessing Dictionary Items**
You can access values using the key in square brackets or the `get()` method.

**Examples from the Lesson Note:**
```python
x = thisdict["model"]
x = thisdict.get("model")
```

**Explanation:**
- `thisdict["model"]`: Returns `"Mustang"`. If the key doesn’t exist, it causes an error.
- `thisdict.get("model")`: Also returns `"Mustang"`, but if the key doesn’t exist, it returns `None` instead of an error.
- It’s like asking a shopkeeper for the price of an item by name, and `get()` is safer because it won’t “crash” if the item isn’t listed.

### **Getting Keys, Values, and Items**
- `keys()`: Returns a list of all keys, e.g., `['brand', 'model', 'year']`.
- `values()`: Returns a list of all values, e.g., `['Ford', 'Mustang', 1964]`.
- `items()`: Returns a list of tuples, each containing a key:value pair, e.g., `[('brand', 'Ford'), ('model', 'Mustang'), ('year', 1964)]`.

**Example from the Lesson Note:**
```python
car = {
  "brand": "Ford",
  "model": "Mustang",
  "year": 1964
}
x = car.keys()
print(x)  # Output: dict_keys(['brand', 'model', 'year'])
car["color"] = "white"
print(x)  # Output: dict_keys(['brand', 'model', 'year', 'color'])
```

**Explanation:**
- `car.keys()`: Returns a view of the keys. When you add a new key (`"color"`), the view updates automatically.
- It’s like a shopkeeper’s list of item names that updates when new stock arrives.

### **Checking if a Key Exists**
Use the `in` keyword to check if a key is in the dictionary.

**Example from the Lesson Note:**
```python
if "model" in thisdict:
  print("Yes, 'model' is one of the keys in the thisdict dictionary")
```

**Explanation:**
- `"model" in thisdict`: Returns `True` if `"model"` is a key, `False` otherwise.
- It’s like checking if “Garri” is listed in a market inventory.

### **Changing Dictionary Items**
You can update values using the key or the `update()` method.

**Examples from the Lesson Note:**
```python
thisdict["year"] = 2018
thisdict.update({"year": 2020})
```

**Explanation:**
- `thisdict["year"] = 2018`: Changes the value of `"year"` to `2018`.
- `thisdict.update({"year": 2020})`: Updates `"year"` to `2020`. The `update()` method takes a dictionary or key:value pairs.
- It’s like updating the price of an item when the market price changes.

### **Adding Dictionary Items**
Add new key:value pairs using a new key or `update()`.

**Examples from the Lesson Note:**
```python
thisdict["color"] = "red"
thisdict.update({"color": "red"})
```

**Explanation:**
- `thisdict["color"] = "red"`: Adds a new key:value pair.
- `thisdict.update({"color": "red"})`: Does the same, but can add multiple pairs at once.
- It’s like adding a new item to a shop’s inventory list.

### **Removing Dictionary Items**
You can remove items using `pop()`, `popitem()`, `del`, or `clear()`.

**Examples from the Lesson Note:**
```python
thisdict.pop("model")  # Removes "model": "Mustang"
thisdict.popitem()     # Removes the last item
del thisdict["model"]  # Removes "model": "Mustang"
thisdict.clear()       # Empties the dictionary
del thisdict           # Deletes the entire dictionary
```

**Explanation:**
- `pop("model")`: Removes the key `"model"` and its value.
- `popitem()`: Removes the last key:value pair (random in Python 3.6 or earlier).
- `del thisdict["model"]`: Removes the specified key.
- `thisdict.clear()`: Removes all items, leaving an empty dictionary `{}`.
- `del thisdict`: Deletes the dictionary entirely, causing an error if you try to access it.
- It’s like removing an item from a shop’s stock list or clearing the entire list.

### **Looping Through Dictionaries**
You can loop through keys, values, or both using `for` loops.

**Examples from the Lesson Note:**
```python
for x in thisdict:
  print(x)  # Prints keys

for x in thisdict.values():
  print(x)  # Prints values

for x, y in thisdict.items():
  print(x, y)  # Prints keys and values
```

**Explanation:**
- `for x in thisdict`: Loops through keys (`"brand"`, `"model"`, `"year"`).
- `for x in thisdict.values()`: Loops through values (`"Ford"`, `"Mustang"`, `1964`).
- `for x, y in thisdict.items()`: Loops through key:value pairs, e.g., `"brand"`, `"Ford"`.
- It’s like a shopkeeper listing all item names, prices, or both from their inventory.

**Nigerian Example:**
```python
market = {
    "item": "Rice",
    "price": 2500,
    "quantity": 10
}
for item, detail in market.items():
    print(f"{item}: {detail}")
```
Output:
```
item: Rice
price: 2500
quantity: 10
```
This is like displaying a market stall’s inventory one item at a time.

### **Copying Dictionaries**
You can’t copy a dictionary with `dict2 = dict1` because it creates a reference. Use `copy()` or `dict()` instead.

**Examples from the Lesson Note:**
```python
mydict = thisdict.copy()
mydict = dict(thisdict)
```

**Explanation:**
- `thisdict.copy()`: Creates a new, independent copy of `thisdict`.
- `dict(thisdict)`: Does the same.
- It’s like photocopying a shop’s inventory list so you can edit the copy without changing the original.

### **Nested Dictionaries**
A dictionary can contain other dictionaries.

**Example from the Lesson Note:**
```python
myfamily = {
  "child1" : {
    "name" : "Emil",
    "year" : 2004
  },
  "child2" : {
    "name" : "Tobias",
    "year" : 2007
  },
  "child3" : {
    "name" : "Linus",
    "year" : 2011
  }
}
print(myfamily["child2"]["name"])  # Output: Tobias
```

**Explanation:**
- `myfamily`: A dictionary where each value is another dictionary.
- `myfamily["child2"]["name"]`: Accesses the `"name"` key inside the `"child2"` dictionary, returning `"Tobias"`.
- It’s like a school record where each student has their own mini-record with details like name and age.

**Nigerian Example:**
```python
classroom = {
    "student1": {
        "name": "Amina",
        "age": 15,
        "grade": "SS1"
    },
    "student2": {
        "name": "Chidi",
        "age": 16,
        "grade": "SS2"
    }
}
print(classroom["student1"]["name"])  # Output: Amina
```
This is like checking a student’s name in a school’s class register.

### **Looping Through Nested Dictionaries**
**Example from the Lesson Note:**
```python
for x, obj in myfamily.items():
  print(x)
  for y in obj:
    print(y + ':', obj[y])
```

**Explanation:**
- `for x, obj in myfamily.items()`: Loops through the outer dictionary’s keys (`"child1"`, `"child2"`, `"child3"`) and values (nested dictionaries).
- `for y in obj`: Loops through the keys of the nested dictionary (`"name"`, `"year"`).
- `obj[y]`: Gets the value for each key.
- Output example:
  ```
  child1
  name: Emil
  year: 2004
  child2
  name: Tobias
  year: 2007
  child3
  name: Linus
  year: 2011
  ```
- It’s like a teacher reading out each student’s details from a class register.

### **Dictionary Methods**
The lesson lists several dictionary methods, explained here with Nigerian context:
- `clear()`: Empties the dictionary, like clearing a shop’s inventory list.
- `copy()`: Copies the dictionary, like duplicating a market price list.
- `fromkeys()`: Creates a dictionary with specified keys and one value for all, e.g., `dict.fromkeys(["item1", "item2"], 0)` for a shop starting with zero stock.
- `get()`: Safely gets a value, like checking a price without crashing if the item isn’t listed.
- `items()`: Returns key:value pairs, like listing a shop’s full inventory.
- `keys()`: Returns keys, like listing item names only.
- `pop()`: Removes a specific key:value pair, like removing an item from stock.
- `popitem()`: Removes the last pair, like selling the last item added to stock.
- `setdefault()`: Gets a value or adds it if it doesn’t exist, like adding a default price for a new item.
- `update()`: Updates or adds key:value pairs, like updating a shop’s price list.
- `values()`: Returns values, like listing all prices in a shop.

**Minimal Example for Beginners (No Example in Note):**
```python
shop = {
    "item": "Garri",
    "price": 1000
}
print(shop.get("price"))  # Output: 1000
shop.update({"quantity": 5})
print(shop)  # Output: {'item': 'Garri', 'price': 1000, 'quantity': 5}
```
This shows how to safely access and update a shop’s inventory, relatable to Nigerian students.

---

## **Section 2 – Class Exercise**

This exercise is designed to be **real-world, Nigerian-themed, and fun**, allowing students to practice dictionaries in a way they can boast about to peers. It builds on the concepts of creating, accessing, and updating dictionaries.

### **Exercise: Build a “Market Price Checker”**
Imagine you’re helping a market trader in Lagos keep track of their goods. Create a program that:
1. Stores at least three items and their prices in a dictionary.
2. Asks the user to input an item name.
3. Checks if the item exists in the dictionary and prints its price. If it doesn’t exist, print “Item not found.”
4. Allows the user to update the price of an item by entering a new price.

**Step-by-Step Guidance:**
1. Create a dictionary with at least three items (e.g., `"Rice": 2500`, `"Beans": 3000`, `"Yam": 1500`).
2. Use `input()` to ask the user for an item name and store it in a variable.
3. Use the `get()` method or `in` keyword to check if the item exists and print its price.
4. Ask the user if they want to update the price of an item. If yes, use `input()` to get the item name and new price, then update the dictionary using `update()` or key assignment.
5. Print the updated dictionary to show the changes.

**Why It’s Fun**: Students can show off a program that feels like a real tool a market trader could use, like checking or updating prices at Computer Village or Balogun Market.

**No Solution Provided**: Students should try writing the code themselves, experimenting with dictionaries, `input()`, and conditionals (if learned previously).

---

## **Section 3 – Weekly Project**

This project combines dictionaries with earlier concepts (e.g., input/output, conditionals) to create a **fun, practical, and Nigerian-themed** program that students will be proud to share.

### **Weekly Project: Danfo Bus Passenger Tracker**
Create a program that helps a danfo bus driver in Lagos keep track of passengers and their fares based on their destination. The program should:
1. Store passenger details (name and destination) in a dictionary.
2. Use a nested dictionary to store fare details for each destination.
3. Allow the driver to check a passenger’s fare or add a new passenger.
4. Print the total number of passengers and their details.

**Project Brief and Milestones:**
1. **Create the Dictionary Structure**:
   - Make a nested dictionary where each passenger is a key, and their value is another dictionary with `"name"` and `"destination"`.
   - Example: `{"passenger1": {"name": "Amina", "destination": "CMS"}}`.
   - Include a separate dictionary for fares, e.g., `fares = {"CMS": 200, "Ojota": 150, "Ikeja": 100}`.

2. **Input Passenger Details**:
   - Ask the user to input a passenger’s name and destination using `input()`.
   - Add these details to the passenger dictionary using `update()` or key assignment.

3. **Check Fares**:
   - Ask the user to input a passenger’s ID (e.g., `"passenger1"`) and display their name, destination, and fare using the `fares` dictionary.
   - Use `get()` to safely handle cases where the destination or passenger doesn’t exist.

4. **Display Summary**:
   - Use `len()` to count the total number of passengers.
   - Loop through the dictionary using `items()` to print each passenger’s details.

**Example Interaction**:
```
Enter passenger ID: passenger1
Enter name: Amina
Enter destination (CMS, Ojota, Ikeja): CMS
Passenger added!

Enter passenger ID to check fare: passenger1
Name: Amina, Destination: CMS, Fare: ₦200

Total passengers: 1
Passenger Details:
passenger1: Name: Amina, Destination: CMS
```

**Why It’s Exciting**: This project feels like a real tool a danfo driver could use, and students can proudly show it to friends, saying, “I built a passenger tracker for Lagos buses!” It’s relatable to daily life in Nigeria and combines dictionaries with input/output and conditionals.

**Extensions for Fun**:
- Add a feature to calculate the total fares collected.
- Allow the driver to remove a passenger when they alight using `pop()`.

**No Solution Provided**: Students should experiment with the concepts to build the program, fostering creativity and problem-solving.

---

This response covers the entire lesson note in detail, uses Nigerian-themed examples to make concepts relatable, and provides engaging activities that make students proud to share their work. Let me know if you need further clarification or additional exercises!