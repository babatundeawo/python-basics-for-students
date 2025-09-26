# **Python Sets: Party Guest List Manager – Code Solution and Explanation**

This document provides the code solution for the **Party Guest List Manager** class exercise from the Python Sets lesson, tailored for Nigerian beginners as per the Nigeria-Focused AI Instructional Framework. The exercise involves creating a program to manage a unique list of guests for an Owambe party using a Python set. Below, the solution is presented first, followed by a detailed explanation of each part, ensuring clarity and relatability with Nigerian-themed context.

---

## **Code Solution**

```python
# Create a set of initial guests for the Owambe party
guest_list = {"Tunde", "Amaka", "Chinedu"}

# Add a new guest to the list
guest_list.add("Fatima")

# Print the number of guests
print(f"Number of guests invited: {len(guest_list)}")

# Check if Amaka is in the guest list
if "Amaka" in guest_list:
    print("Amaka is invited!")
else:
    print("Amaka is not invited.")

# Remove Chinedu from the guest list
guest_list.discard("Chinedu")

# Print the final guest list
print(f"Final guest list: {guest_list}")

# Test adding a duplicate guest (Tunde) to show no duplicates are allowed
guest_list.add("Tunde")
print(f"Guest list after trying to add Tunde again: {guest_list}")
```

**Sample Output** (order may vary due to sets being unordered):
```
Number of guests invited: 4
Amaka is invited!
Final guest list: {'Tunde', 'Amaka', 'Fatima'}
Guest list after trying to add Tunde again: {'Tunde', 'Amaka', 'Fatima'}
```

---

## **Explanation**

This section explains each part of the code solution step-by-step, tying it to Nigerian experiences to make it clear and engaging for beginners. The explanation follows the framework’s guidelines: simple language, progressive steps, and confidence-building examples.

### **Step 1: Creating the Set**
```python
guest_list = {"Tunde", "Amaka", "Chinedu"}
```
- **What it does**: Creates a set named `guest_list` with three guest names: "Tunde", "Amaka", and "Chinedu".
- **Why it’s a set**: Sets use curly brackets `{}` and ensure no duplicate names are stored, like making sure you don’t invite the same person twice to an Owambe party in Lagos.
- **Relatable analogy**: This is like writing a list of unique guests on a party invitation card. If you accidentally write "Tunde" twice, the set keeps only one.

### **Step 2: Adding a New Guest**
```python
guest_list.add("Fatima")
```
- **What it does**: Uses the `add()` method to include "Fatima" in the `guest_list` set.
- **How it works**: The `add()` method adds a single item to the set. If "Fatima" was already in the set, it wouldn’t be added again (no duplicates).
- **Relatable analogy**: This is like calling a new friend, Fatima, to join your party. The set ensures her name is only listed once, even if you try to add it again.

### **Step 3: Counting the Number of Guests**
```python
print(f"Number of guests invited: {len(guest_list)}")
```
- **What it does**: Uses the `len()` function to count how many guests are in the set and prints the result (e.g., `4`).
- **How it works**: `len(guest_list)` returns the number of items in the set, which is now 4 (Tunde, Amaka, Chinedu, Fatima).
- **Relatable analogy**: This is like counting how many people you’ve invited to your party, similar to checking how many plates of jollof rice you need to prepare.

### **Step 4: Checking if a Guest is Invited**
```python
if "Amaka" in guest_list:
    print("Amaka is invited!")
else:
    print("Amaka is not invited.")
```
- **What it does**: Uses the `in` keyword to check if "Amaka" is in the `guest_list`. If true, it prints “Amaka is invited!”; otherwise, it prints “Amaka is not invited.”
- **How it works**: The `in` keyword checks for the presence of an item in the set. Since "Amaka" is in `guest_list`, the condition is true, and the first message is printed.
- **Relatable analogy**: This is like checking your party invitation list to confirm if Amaka is coming, similar to verifying if a friend’s name is on a school trip list.

### **Step 5: Removing a Guest**
```python
guest_list.discard("Chinedu")
```
- **What it does**: Uses the `discard()` method to remove "Chinedu" from the `guest_list`.
- **Why use `discard()`?**: Unlike `remove()`, `discard()` doesn’t raise an error if the item isn’t in the set, making it safer for beginners. Here, "Chinedu" is removed because they can’t attend.
- **Relatable analogy**: This is like crossing out a guest’s name from your party list because they sent a message saying they’re unavailable, similar to updating a guest list for an Owambe.

### **Step 6: Printing the Final Guest List**
```python
print(f"Final guest list: {guest_list}")
```
- **What it does**: Prints the updated `guest_list`, which now contains `{'Tunde', 'Amaka', 'Fatima'}` (order may vary).
- **How it works**: The `print()` function displays the set. Since sets are unordered, the names might appear in any order.
- **Relatable analogy**: This is like showing your friends the final list of who’s coming to the party, similar to sharing a list of attendees for a school event.

### **Step 7: Testing No Duplicates**
```python
guest_list.add("Tunde")
print(f"Guest list after trying to add Tunde again: {guest_list}")
```
- **What it does**: Tries to add "Tunde" again using `add()` and prints the set to show it remains unchanged.
- **How it works**: Since "Tunde" is already in the set, the `add()` method doesn’t add another copy because sets don’t allow duplicates. The output is still `{'Tunde', 'Amaka', 'Fatima'}`.
- **Relatable analogy**: This is like trying to invite Tunde again to the same party. The set ensures his name isn’t added twice, just like avoiding duplicate names on a WhatsApp group invite.

### **Why This Program Builds Confidence**
- **Practical and relatable**: Managing a guest list feels like planning a real Nigerian Owambe party, something students can relate to and share with friends.
- **Showcases set features**: The code demonstrates key set properties (no duplicates, adding/removing items, checking membership) in a simple, beginner-friendly way.
- **Encourages experimentation**: Students can modify the code (e.g., add more guests or check different names) to see how sets work, building confidence in their Python skills.

---

This solution and explanation provide a complete, beginner-friendly guide to the Party Guest List Manager exercise. The code is simple, uses Nigerian names to make it relatable, and demonstrates set operations in a way that students can proudly share with peers, sparking conversations like “I built a party planner with Python!”