# Solution to Python Weekly Project: Contact Manager

This document provides the solution to the Python weekly project from the Python Functions tutorial, where the task is to create a program that uses functions to manage a contact list with names and details. Below is the solution code, followed by a detailed explanation tailored for beginners.

---

## Solution Code

```python
# contact_manager.py
# This program manages a contact list using functions with arguments and scope

"""
Program: Contact Manager
Author: [Your Name]
Purpose: Demonstrates using functions to add, print, filter, and update contacts
"""

# Global contacts list
contacts = []

# Add a contact with positional-only name and keyword-only phone, email
def add_contact(name, /, *, phone, email):
    if not name or not phone or not email:
        return None  # Validation: non-empty inputs
    if not phone.replace("-", "").isdigit() or len(phone.replace("-", "")) != 10:
        return None  # Validation: 10-digit phone number
    contact = {"name": name, "phone": phone, "email": email}
    contacts.append(contact)
    return contact

# Print all contacts
def print_contacts(contacts):
    if not contacts:
        return "No contacts available"
    output = "All Contacts:\n"
    for contact in contacts:
        output += f"{contact['name']}: {contact['phone']}, {contact['email']}\n"
    return output

# Filter contacts by criteria
def filter_contacts(*contacts, **criteria):
    filtered = []
    for contact in contacts:
        match = True
        for key, value in criteria.items():
            if contact.get(key) != value:
                match = False
                break
        if match:
            filtered.append(contact)
    return filtered

# Update contact details
def update_contact(contact, **updates):
    if not contact:
        return None
    for key, value in updates.items():
        if key in contact:
            if key == "phone" and (not value.replace("-", "").isdigit() or len(value.replace("-", "")) != 10):
                return None  # Validation: 10-digit phone
            contact[key] = value
    return contact

# Main program
print("Contact Manager:")

# Add contacts
contact1 = add_contact("Emil", phone="123-456-7890", email="emil@example.com")
print(f"Added: {contact1}")
contact2 = add_contact("Tobias", phone="987-654-3210", email="tobias@example.com")
print(f"Added: {contact2}")

# Print all contacts
print(print_contacts(contacts))

# Filter contacts by phone
filtered = filter_contacts(*contacts, phone="123-456-7890")
print("Filtered Contacts (phone=123-456-7890):")
for contact in filtered:
    print(f"{contact['name']}: {contact['phone']}, {contact['email']}")

# Update a contact
updated = update_contact(contact1, phone="555-555-5555")
print("Updated Contact:")
print(updated)

# Validate inputs
if None in contacts or None in [contact1, contact2, updated]:
    print("Some inputs were invalid")
else:
    print("All inputs valid")
```

**Expected Output**:
```
Contact Manager:
Added: {'name': 'Emil', 'phone': '123-456-7890', 'email': 'emil@example.com'}
Added: {'name': 'Tobias', 'phone': '987-654-3210', 'email': 'tobias@example.com'}
All Contacts:
Emil: 123-456-7890, emil@example.com
Tobias: 987-654-3210, tobias@example.com
Filtered Contacts (phone=123-456-7890):
Emil: 123-456-7890, emil@example.com
Updated Contact:
{'name': 'Emil', 'phone': '555-555-5555', 'email': 'emil@example.com'}
All inputs valid
```

---

## Explanation

### Objective
The project requires creating a Python program (`contact_manager.py`) that:
- Defines a function `add_contact(name, /, *, phone, email)` to return a contact dictionary.
- Defines a function `print_contacts(contacts)` to print all contacts.
- Defines a function `filter_contacts(*contacts, **criteria)` to filter contacts by criteria.
- Defines a function `update_contact(contact, **updates)` to update contact details.
- Uses a global `contacts` list to store contacts.
- Validates inputs (e.g., non-empty name, 10-digit phone number).
- Calls functions to add, print, filter, and update contacts.
- Runs correctly with `python contact_manager.py`.

### Line-by-Line Breakdown
Let’s walk through the code to understand each part, its input, output, and purpose:

1. **File Creation**:
   - The code is saved in a file named `contact_manager.py`. This ensures Python recognizes it as a Python script when you run `python contact_manager.py`.

2. **Single-Line Comment**:
   ```python
   # contact_manager.py
   # This program manages a contact list using functions with arguments and scope
   ```
   - **Purpose**: Describes the file and program purpose. Ignored by Python.
   - **Input**: None.
   - **Output**: None.
   - **Side Effects**: None.

3. **Multiline Comment**:
   ```python
   """
   Program: Contact Manager
   Author: [Your Name]
   Purpose: Demonstrates using functions to add, print, filter, and update contacts
   """
   ```
   - **Purpose**: Provides detailed documentation. Ignored by Python since it’s not assigned.
   - **Input**: None.
   - **Output**: None.
   - **Side Effects**: None.

4. **Global Contacts List**:
   ```python
   contacts = []
   ```
   - **Purpose**: Initializes a global list to store contact dictionaries.
   - **Input**: None.
   - **Output**: None.
   - **Side Effects**: Creates empty list `contacts`.

5. **Function: add_contact**:
   ```python
   def add_contact(name, /, *, phone, email):
       if not name or not phone or not email:
           return None
       if not phone.replace("-", "").isdigit() or len(phone.replace("-", "")) != 10:
           return None
       contact = {"name": name, "phone": phone, "email": email}
       contacts.append(contact)
       return contact
   ```
   - **Purpose**: Adds a contact to the global `contacts` list and returns the contact dictionary.
   - **Input**: `name` (positional-only string), `phone`, `email` (keyword-only strings).
   - **Output**: Dictionary (e.g., `{"name": "Emil", "phone": "123-456-7890", "email": "emil@example.com"}`) or `None` if invalid.
   - **Side Effects**: Appends to `contacts`.
   - **Explanation**:
     - `name, /, *, phone, email`: Enforces positional-only `name` and keyword-only `phone`, `email`.
     - `if not name or not phone or not email`: Validates non-empty inputs.
     - `phone.replace("-", "").isdigit()`: Ensures phone is numeric (ignoring hyphens).
     - `len(phone.replace("-", "")) != 10`: Ensures 10-digit phone number.
     - `contact = {"name": name, ...}`: Creates dictionary.
     - `contacts.append(contact)`: Adds to global list.
     - `return contact`: Returns the new contact.

6. **Function: print_contacts**:
   ```python
   def print_contacts(contacts):
       if not contacts:
           return "No contacts available"
       output = "All Contacts:\n"
       for contact in contacts:
           output += f"{contact['name']}: {contact['phone']}, {contact['email']}\n"
       return output
   ```
   - **Purpose**: Returns a string of all contacts formatted for printing.
   - **Input**: `contacts` (list of dictionaries).
   - **Output**: Formatted string (e.g., `Emil: 123-456-7890, emil@example.com\n...`).
   - **Side Effects**: None.
   - **Explanation**:
     - `if not contacts`: Handles empty list.
     - `output = "All Contacts:\n"`: Initializes output string.
     - `for contact in contacts`: Iterates over contacts.
     - `output += f"{contact['name']}..."`: Adds formatted contact details.

7. **Function: filter_contacts**:
   ```python
   def filter_contacts(*contacts, **criteria):
       filtered = []
       for contact in contacts:
           match = True
           for key, value in criteria.items():
               if contact.get(key) != value:
                   match = False
                   break
           if match:
               filtered.append(contact)
       return filtered
   ```
   - **Purpose**: Filters contacts based on keyword criteria.
   - **Input**: `*contacts` (tuple of dictionaries), `**criteria` (dictionary of key-value pairs, e.g., `phone="123-456-7890"`).
   - **Output**: List of matching contact dictionaries.
   - **Side Effects**: None.
   - **Explanation**:
     - `filtered = []`: Initializes result list.
     - `for contact in contacts`: Iterates over contacts.
     - `match = True`: Assumes match until proven otherwise.
     - `for key, value in criteria.items()`: Checks each criterion.
     - `contact.get(key) != value`: Compares contact field to criterion.
     - `filtered.append(contact)`: Adds matching contacts.

8. **Function: update_contact**:
   ```python
   def update_contact(contact, **updates):
       if not contact:
           return None
       for key, value in updates.items():
           if key in contact:
               if key == "phone" and (not value.replace("-", "").isdigit() or len(value.replace("-", "")) != 10):
                   return None
               contact[key] = value
       return contact
   ```
   - **Purpose**: Updates contact dictionary with new values.
   - **Input**: `contact` (dictionary), `**updates` (dictionary of key-value pairs).
   - **Output**: Updated contact dictionary or `None` if invalid.
   - **Side Effects**: Modifies `contact`.
   - **Explanation**:
     - `if not contact`: Handles invalid input.
     - `for key, value in updates.items()`: Iterates over updates.
     - `if key in contact`: Ensures valid keys.
     - Phone validation ensures 10-digit numeric phone.
     - `contact[key] = value`: Updates field.

9. **Main Program**:
   ```python
   print("Contact Manager:")
   contact1 = add_contact("Emil", phone="123-456-7890", email="emil@example.com")
   print(f"Added: {contact1}")
   contact2 = add_contact("Tobias", phone="987-654-3210", email="tobias@example.com")
   print(f"Added: {contact2}")
   print(print_contacts(contacts))
   filtered = filter_contacts(*contacts, phone="123-456-7890")
   print("Filtered Contacts (phone=123-456-7890):")
   for contact in filtered:
       print(f"{contact['name']}: {contact['phone']}, {contact['email']}")
   updated = update_contact(contact1, phone="555-555-5555")
   print("Updated Contact:")
   print(updated)
   if None in contacts or None in [contact1, contact2, updated]:
       print("Some inputs were invalid")
   else:
       print("All inputs valid")
   ```
   - **Purpose**: Demonstrates all functions.
   - **Explanation**:
     - Adds two contacts using `add_contact`.
     - Prints all contacts with `print_contacts`.
     - Filters contacts by phone number.
     - Updates a contact’s phone number.
     - Validates that no `None` values were returned.

### Visual Description
When you run `python contact_manager.py` in the terminal, the output is:
```
Contact Manager:
Added: {'name': 'Emil', 'phone': '123-456-7890', 'email': 'emil@example.com'}
Added: {'name': 'Tobias', 'phone': '987-654-3210', 'email': 'tobias@example.com'}
All Contacts:
Emil: 123-456-7890, emil@example.com
Tobias: 987-654-3210, tobias@example.com
Filtered Contacts (phone=123-456-7890):
Emil: 123-456-7890, emil@example.com
Updated Contact:
{'name': 'Emil', 'phone': '555-555-5555', 'email': 'emil@example.com'}
All inputs valid
```
Each section is clearly labeled, showing added contacts, all contacts, filtered contacts, updated contact, and validation result.

### Common Mistakes and Fixes
1. **Incorrect Argument Type**:
   - **Mistake**:
     ```python
     add_contact("Emil", "123-456-7890", "emil@example.com")  # Positional instead of keyword
     ```
   - **Error**: `TypeError` (phone, email must be keyword-only).
   - **Fix**: Use keyword arguments:
     ```python
     add_contact("Emil", phone="123-456-7890", email="emil@example.com")
     ```
2. **Missing Validation**:
   - **Mistake**:
     ```python
     def add_contact(name, /, *, phone, email):
         contact = {"name": name, "phone": phone, "email": email}
         contacts.append(contact)
         return contact
     ```
   - **Error**: Accepts invalid inputs (e.g., empty strings, invalid phone).
   - **Fix**: Add validation:
     ```python
     if not name or not phone or not email:
         return None
     if not phone.replace("-", "").isdigit() or len(phone.replace("-", "")) != 10:
         return None
     ```
3. **Modifying Global List Incorrectly**:
   - **Mistake**:
     ```python
     def add_contact(name, /, *, phone, email):
         contact = {"name": name, "phone": phone, "email": email}
         return contact  # Forgets to append
     ```
   - **Error**: Contacts not stored in `contacts`.
   - **Fix**: Append to global list:
     ```python
     contacts.append(contact)
     ```
4. **Incorrect Filtering Logic**:
   - **Mistake**:
     ```python
     def filter_contacts(*contacts, **criteria):
         filtered = []
         for contact in contacts:
             if contact["phone"] == criteria["phone"]:  # Hardcoded key
                 filtered.append(contact)
         return filtered
     ```
   - **Error**: Fails for other criteria (e.g., `email`).
   - **Fix**: Use dynamic criteria checking:
     ```python
     for key, value in criteria.items():
         if contact.get(key) != value:
             match = False
             break
     ```
5. **Wrong File Extension**:
   - **Mistake**: Saving as `contact_manager.txt`.
   - **Fix**: Save as `contact_manager.py` and run with `python contact_manager.py`.

### Validation Check
To confirm the program works:
1. Save the code in `contact_manager.py`.
2. Open a terminal, navigate to the file’s directory, and run `python contact_manager.py`.
3. Verify the output matches: two contacts added, all contacts listed, one filtered contact, updated contact, and `"All inputs valid"`.
4. Test with invalid inputs (e.g., `add_contact("", phone="123-456-7890", email="emil@example.com")`):
   - Should return `None` and print `"Some inputs were invalid"`.
5. Test with invalid phone (e.g., `phone="123"`):
   - Should return `None`.
6. Add `print(type(contacts))` to confirm `contacts` is a list (`<class 'list'>`).

### Extension Idea Implementation
For learners interested in the extension ideas:
- **Delete Contact Function**:
  ```python
  def delete_contact(name):
      global contacts
      for contact in contacts:
          if contact["name"] == name:
              contacts.remove(contact)
              return True
      return False
  print("Delete Emil:", delete_contact("Emil"))
  print(print_contacts(contacts))
  ```
  - Add after main program. Outputs: `Delete Emil: True`, then lists remaining contacts.
- **Process Multiple Updates**:
  ```python
  def process_multiple_updates(contact, updates_list):
      for updates in updates_list:
          update_contact(contact, **updates)
      return contact
  updates = [{"phone": "111-222-3333"}, {"email": "new@example.com"}]
  print("Multiple Updates:", process_multiple_updates(contact2, updates))
  ```
  - Add after main program. Updates `contact2` sequentially.

### Research Prompts Answered
- **How does the LEGB rule affect variable access in nested functions?**
  - The LEGB rule (Local, Enclosing, Global, Built-in) determines variable lookup. In `filter_contacts`, `contacts` is local (from `*contacts`), while the global `contacts` list is accessed in `add_contact`. Using `global contacts` in `add_contact` ensures modifications affect the global list.
- **Why are functions preferred over repeated code blocks?**
  - Functions reduce repetition, improve readability, and make code easier to maintain. For example, `add_contact` encapsulates contact creation and validation, reusable across multiple calls.

### One-Line Takeaway
This program uses functions with positional-only, keyword-only, `*args`, and `**kwargs` to manage a contact list, with validation and global scope handling.