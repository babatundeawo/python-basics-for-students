# **Python Sets: Nigeria-Focused Beginner’s Guide**

This document provides a comprehensive explanation of Python sets, tailored for complete beginners in Nigeria. It follows the Nigeria-Focused AI Instructional Framework, ensuring clarity, relatability, and engagement through Nigerian-themed examples. The content is divided into three sections: **Explanations**, **Class Exercise**, and **Weekly Project**.

---

## **Section 1 – Explanations**

This section breaks down the concepts of Python sets from the lesson note, using simple English and relatable Nigerian examples. Each concept is explained step-by-step, with code examples expanded or created to illustrate the ideas.

### **What is a Set?**
A set in Python is like a basket of fruits you buy from a market in Lagos, but it only keeps one of each type of fruit, and you can’t arrange them in any specific order. Sets are used to store multiple items in one variable and have these properties:
- **Unordered**: The items don’t have a fixed position, like customers queuing at a danfo bus stop – you can’t predict the order they’ll appear.
- **Unchangeable**: You can’t modify an item once it’s in the set (e.g., you can’t change "mango" to "orange"), but you can add or remove items.
- **No duplicates**: If you try to add two "apples," the set keeps only one, like how you can’t list the same phone number twice in your contact list.

Sets are written with curly brackets `{}`. Here’s an example:

```python
thisset = {"apple", "banana", "cherry"}
print(thisset)
```

**Explanation of the code**:
- `thisset` is the name of the set, like labeling a bag of groceries.
- `{"apple", "banana", "cherry"}` are the items in the set, like different fruits in your market basket.
- `print(thisset)` displays the set, but the order of items might change each time you run it (e.g., `{'banana', 'apple', 'cherry'}`), because sets are unordered.

**Relatable Example**: Imagine you’re making a list of unique food items to buy for a family party in Abuja. You write "rice," "beans," and "rice" again by mistake. A set would automatically keep only one "rice," ensuring no duplicates.

---

### **Set Items: Unordered, Unchangeable, No Duplicates**
- **Unordered**: You can’t access items by index (like `thisset[0]`) because there’s no fixed order. It’s like picking a random fruit from a basket without knowing which one you’ll get.
- **Unchangeable**: Once an item like "apple" is in the set, you can’t change it to "mango." However, you can add new items or remove existing ones.
- **No Duplicates**: Sets automatically remove duplicates. For example:

```python
thisset = {"apple", "banana", "cherry", "apple"}
print(thisset)
```

**Output**: `{'apple', 'banana', 'cherry'}`  
**Explanation**: The second `"apple"` is ignored because sets don’t allow duplicates, just like you wouldn’t list the same guest twice for an Owambe party.

- **Special Case: True/1 and False/0**:
  - In sets, `True` is treated as `1`, and `False` is treated as `0`. For example:

```python
thisset = {"apple", "banana", "cherry", True, 1, 2}
print(thisset)
```

**Output**: `{'apple', 'banana', 'cherry', True, 2}`  
**Explanation**: `1` is ignored because it’s considered the same as `True`. Similarly:

```python
thisset = {"apple", "banana", "cherry", False, True, 0}
print(thisset)
```

**Output**: `{'apple', 'banana', 'cherry', True}`  
**Explanation**: `0` is ignored because it’s the same as `False`. This is like how MTN might treat two identical recharge PINs as one.

---

### **Getting the Length of a Set**
You can find out how many items are in a set using the `len()` function, just like counting how many items you bought at Oyingbo Market.

```python
thisset = {"apple", "banana", "cherry"}
print(len(thisset))
```

**Output**: `3`  
**Explanation**: The set has three items. It’s like checking how many different snacks you packed for a school lunch.

---

### **Set Items – Data Types**
Sets can hold different data types, like strings, integers, and booleans. For example:

```python
set1 = {"abc", 34, True, 40, "male"}
print(set1)
```

**Explanation**:
- `"abc"` and `"male"` are strings (text), like names or descriptions.
- `34` and `40` are integers (numbers), like ages or prices.
- `True` is a boolean, like answering “yes” to a question.
- This is like a set of details on a JAMB registration form: your name (string), age (integer), and whether you’re male or female (string or boolean).

---

### **Checking the Type of a Set**
You can check if a variable is a set using the `type()` function:

```python
myset = {"apple", "banana", "cherry"}
print(type(myset))
```

**Output**: `<class 'set'>`  
**Explanation**: This confirms `myset` is a set, like verifying that a bag contains only unique items.

---

### **Using the set() Constructor**
You can create a set using the `set()` constructor, which takes an iterable like a tuple or list. For example:

```python
thisset = set(("apple", "banana", "cherry"))
print(thisset)
```

**Explanation**:
- `("apple", "banana", "cherry")` is a tuple (note the round brackets).
- `set()` converts the tuple into a set, removing any duplicates and making it unordered.
- This is like turning a list of party guests written on paper into a unique set of names.

---

### **Accessing Set Items**
You can’t access set items by index because they’re unordered. Instead, you can:
- **Loop through the set** using a `for` loop:

```python
thisset = {"apple", "banana", "cherry"}
for x in thisset:
    print(x)
```

**Output** (order may vary):
```
apple
banana
cherry
```

**Explanation**: The `for` loop goes through each item, like checking each item in your market basket one by one.

- **Check if an item exists** using `in` or `not in`:

```python
thisset = {"apple", "banana", "cherry"}
print("banana" in thisset)
print("banana" not in thisset)
```

**Output**:
```
True
False
```

**Explanation**: `"banana" in thisset` checks if "banana" is in the set, like checking if "suya" is on a restaurant menu. `"banana" not in thisset` checks if it’s absent.

---

### **Adding Items to a Set**
- **Using `add()`**:

```python
thisset = {"apple", "banana", "cherry"}
thisset.add("orange")
print(thisset)
```

**Output**: `{'apple', 'banana', 'cherry', 'orange'}`  
**Explanation**: `add()` puts a new item into the set, like adding a new snack to your party menu.

- **Using `update()`**:

```python
thisset = {"apple", "banana", "cherry"}
tropical = {"pineapple", "mango", "papaya"}
thisset.update(tropical)
print(thisset)
```

**Output**: `{'apple', 'banana', 'cherry', 'pineapple', 'mango', 'papaya'}`  
**Explanation**: `update()` adds all items from another set (or any iterable, like a list or tuple) to the original set, like combining two market baskets into one.

- **Adding from a list**:

```python
thisset = {"apple", "banana", "cherry"}
mylist = ["kiwi", "orange"]
thisset.update(mylist)
print(thisset)
```

**Output**: `{'apple', 'banana', 'cherry', 'kiwi', 'orange'}`  
**Explanation**: The list items are added to the set, ensuring no duplicates.

---

### **Removing Items from a Set**
- **Using `remove()`**:

```python
thisset = {"apple", "banana", "cherry"}
thisset.remove("banana")
print(thisset)
```

**Output**: `{'apple', 'cherry'}`  
**Explanation**: `remove()` deletes the specified item. If the item isn’t in the set, it raises an error, like trying to remove a non-existent item from your shopping list.

- **Using `discard()`**:

```python
thisset = {"apple", "banana", "cherry"}
thisset.discard("banana")
print(thisset)
```

**Output**: `{'apple', 'cherry'}`  
**Explanation**: `discard()` is like `remove()`, but it doesn’t raise an error if the item isn’t found, making it safer.

- **Using `pop()`**:

```python
thisset = {"apple", "banana", "cherry"}
x = thisset.pop()
print(x)
print(thisset)
```

**Output** (item removed is random):
```
apple
{'banana', 'cherry'}
```

**Explanation**: `pop()` removes a random item because sets are unordered. It returns the removed item, like picking a random fruit from a basket.

- **Using `clear()`**:

```python
thisset = {"apple", "banana", "cherry"}
thisset.clear()
print(thisset)
```

**Output**: `set()`  
**Explanation**: `clear()` empties the set, like clearing your market basket after shopping.

- **Using `del`**:

```python
thisset = {"apple", "banana", "cherry"}
del thisset
print(thisset)
```

**Output**: Error (NameError: name 'thisset' is not defined)  
**Explanation**: `del` deletes the entire set, like throwing away the basket itself.

---

### **Joining Sets**
Sets can be combined using methods like `union()`, `intersection()`, `difference()`, and `symmetric_difference()`. These are like managing guest lists for a party.

- **Union**:

```python
set1 = {"a", "b", "c"}
set2 = {1, 2, 3}
set3 = set1.union(set2)
print(set3)
```

**Output**: `{'a', 'b', 'c', 1, 2, 3}`  
**Explanation**: `union()` combines all items from both sets, like inviting everyone from two different party lists. You can also use the `|` operator:

```python
set3 = set1 | set2
```

**Output**: Same as above.

- **Intersection**:

```python
set1 = {"apple", "banana", "cherry"}
set2 = {"google", "microsoft", "apple"}
set3 = set1.intersection(set2)
print(set3)
```

**Output**: `{'apple'}`  
**Explanation**: `intersection()` keeps only items present in both sets, like finding common items in two market lists. You can use `&` instead.  
The `intersection_update()` method modifies the original set:

```python
set1.intersection_update(set2)
print(set1)
```

**Output**: `{'apple'}`

- **Difference**:

```python
set1 = {"apple", "banana", "cherry"}
set2 = {"google", "microsoft", "apple"}
set3 = set1.difference(set2)
print(set3)
```

**Output**: `{'banana', 'cherry'}`  
**Explanation**: `difference()` keeps items in `set1` that aren’t in `set2`, like listing foods unique to one market stall. You can use `-` instead.  
The `difference_update()` method modifies the original set:

```python
set1.difference_update(set2)
print(set1)
```

**Output**: `{'banana', 'cherry'}`

- **Symmetric Difference**:

```python
set1 = {"apple", "banana", "cherry"}
set2 = {"google", "microsoft", "apple"}
set3 = set1.symmetric_difference(set2)
print(set3)
```

**Output**: `{'banana', 'cherry', 'google', 'microsoft'}`  
**Explanation**: `symmetric_difference()` keeps items that are in either set but not both, like listing unique foods from two stalls. You can use `^` instead.  
The `symmetric_difference_update()` method modifies the original set:

```python
set1.symmetric_difference_update(set2)
print(set1)
```

**Output**: `{'banana', 'cherry', 'google', 'microsoft'}`

---

### **Frozenset**
A `frozenset` is like a set, but you can’t add or remove items after creating it – it’s “frozen.” It’s like a guest list for a wedding that’s finalized and can’t be changed.

```python
x = frozenset({"apple", "banana", "cherry"})
print(x)
print(type(x))
```

**Output**:
```
frozenset({'apple', 'banana', 'cherry'})
<class 'frozenset'>
```

**Explanation**: `frozenset()` creates an immutable set. You can still use methods like `union()`, `intersection()`, etc., but not `add()` or `remove()`.

---

### **Set Methods**
The lesson lists several set methods, such as `add()`, `remove()`, `union()`, etc., which have been explained above. Other methods include:
- `isdisjoint()`: Checks if two sets have no items in common.
- `issubset()`: Checks if all items in one set are in another.
- `issuperset()`: Checks if a set contains all items of another set.
- `copy()`: Creates a copy of the set.

**Example**:

```python
set1 = {"apple", "banana"}
set2 = {"apple", "banana", "cherry"}
print(set1.issubset(set2))  # Output: True
```

**Explanation**: `set1` is a subset of `set2` because all its items are in `set2`, like checking if your shopping list is fully covered by a bigger list.

---

## **Section 2 – Class Exercise**

**Exercise: Build a “Party Guest List Manager”**

**Objective**: Create a program that helps manage a unique list of guests for a Nigerian Owambe party using a set. This exercise uses sets to ensure no duplicate guests and practices adding and removing items.

**Steps**:
1. Create a set called `guest_list` with at least three guest names (e.g., "Tunde", "Amaka", "Chinedu").
2. Use the `add()` method to add one more guest (e.g., "Fatima").
3. Use the `len()` function to print how many guests are in the list.
4. Check if a specific guest (e.g., "Amaka") is in the list using the `in` keyword and print a message like “Amaka is invited!” if true.
5. Use the `remove()` or `discard()` method to remove one guest (e.g., "Chinedu") because they can’t attend.
6. Print the final guest list.

**Guidance**:
- Start by creating the set with curly brackets `{}`.
- Use `add()` to include a new guest.
- Use `len()` to count guests.
- Use an `if` statement with `in` to check for a guest.
- Use `remove()` or `discard()` to take out a guest.
- Test your program to ensure no duplicates are added (e.g., try adding "Tunde" again).

**Why It’s Fun**: Students can show off a program that feels like organizing a real party, something they can relate to and share with friends!

---

## **Section 3 – Weekly Project**

**Project: Create a “Market Stall Inventory Tracker”**

**Objective**: Build a program that uses sets to track unique items in two market stalls (e.g., in Mile 12 Market) and perform operations like finding common items, unique items, or combining inventories. This project combines sets with user input (from previous lessons) and set operations like `union()`, `intersection()`, and `difference()`.

**Project Brief**:
You’re helping two traders in Mile 12 Market manage their inventory of goods. Each trader has a set of unique items they sell, and they want to:
- Combine their inventories to see all unique items they can offer together.
- Find items they both sell (common items).
- Identify items unique to each trader.
- Allow adding or removing items based on new stock.

**Milestones**:
1. **Create Two Sets**: Create two sets, `stall1` and `stall2`, with items like "yam", "tomato", "fish", etc. Ensure at least one item is common (e.g., "tomato").
2. **Combine Inventories**: Use `union()` to create a set of all unique items from both stalls and print it.
3. **Find Common Items**: Use `intersection()` to find items both stalls sell and print them.
4. **Find Unique Items**: Use `difference()` to find items unique to `stall1` (not in `stall2`) and vice versa, then print them.
5. **Add New Stock**: Ask the user to input a new item (using `input()` from previous lessons) and add it to `stall1` using `add()`.
6. **Remove an Item**: Ask the user to input an item to remove from `stall2` and use `discard()` to remove it safely.
7. **Display Final Inventories**: Print the updated `stall1` and `stall2`.

**Example Scenario**:
- `stall1 = {"yam", "tomato", "fish"}`
- `stall2 = {"tomato", "pepper", "onion"}`
- Union: `{"yam", "tomato", "fish", "pepper", "onion"}`
- Intersection: `{"tomato"}`
- Difference (stall1 - stall2): `{"yam", "fish"}`
- Add "plantain" to `stall1`, remove "pepper" from `stall2`.

**Why It’s Exciting**: This project feels like running a real market stall, something Nigerian students can relate to. They’ll be proud to show friends a program that manages market goods, sparking conversations like “I built a market inventory tracker with Python!”

**Guidance**:
- Use `input()` to get user inputs for adding/removing items.
- Use set methods like `union()`, `intersection()`, and `difference()`.
- Test with duplicate items to see how sets handle them.
- Print clear messages, e.g., “Stall 1 now has: {stall1}”.

---

This guide covers the entire lesson note on Python sets, using Nigerian-themed examples to make learning engaging and practical for beginners. The class exercise and weekly project encourage students to apply set concepts in fun, relatable ways, fostering confidence and pride in their work.