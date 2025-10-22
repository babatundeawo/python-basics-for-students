# Python Dictionaries for Beginners

This tutorial covers Python dictionaries, including their creation, manipulation, and operations like accessing, updating, and nesting. Below is a beginner-friendly teaching package based on the provided lesson note, designed to guide learners toward intermediate-level mastery with practical examples and exercises.

---

## Section 1 — Topical Explanations

### Learning Goals
- Understand how to create dictionaries using curly brackets `{}` and the `dict()` constructor.
- Learn to access, add, and remove items using methods like `get()`, `update()`, `pop()`, and `popitem()`.
- Explore dictionary properties (ordered, changeable, no duplicate keys) and nested dictionaries.
- Use loops to iterate through keys, values, and key-value pairs.
- Create copies of dictionaries and understand nested dictionary access.

### Creating Dictionaries
Dictionaries store data in key-value pairs, are ordered (since Python 3.7), changeable, and do not allow duplicate keys. They are created using curly brackets `{}` or the `dict()` constructor.

**Example Code**:
```python
# Creating dictionaries
thisdict = {"brand": "Ford", "model": "Mustang", "year": 1964}  # Using curly brackets
print(thisdict)  # Outputs: {'brand': 'Ford', 'model': 'Mustang', 'year': 1964}
mydict = dict(name="John", age=36, country="Norway")  # Using dict() constructor
print(mydict)  # Outputs: {'name': 'John', 'age': 36, 'country': 'Norway'}
print(type(thisdict))  # Outputs: <class 'dict'>
```
- **Line-by-Line Explanation**:
  - `thisdict = {"brand": "Ford", "model": "Mustang", "year": 1964}`: Creates a dictionary with three key-value pairs. **Input**: `{"brand": "Ford", "model": "Mustang", "year": 1964}`. **Output**: None. **Side Effects**: `thisdict` holds the dictionary.
  - `print(thisdict)`: Displays the dictionary. **Output**: `{'brand': 'Ford', 'model': 'Mustang', 'year': 1964}`.
  - `mydict = dict(name="John", age=36, country="Norway")`: Creates a dictionary using `dict()`. **Input**: Keyword arguments. **Output**: None. **Side Effects**: `mydict` holds `{'name': 'John', 'age': 36, 'country': 'Norway'}`.
  - `print(type(thisdict))`: Confirms dictionary type. **Output**: `<class 'dict'>`.
- **Visual Description**: Terminal shows dictionaries with key-value pairs in curly brackets, maintaining order (Python 3.7+).
- **Common Mistake**: Using duplicate keys, e.g., `{"year": 1964, "year": 2020}`.
  - **Error**: No error, but the last value overwrites earlier ones (`{'year': 2020}`).
  - **Fix**: Ensure unique keys.
- **Validation Check**: Verify type with `print(type(thisdict))` (outputs `<class 'dict'>`).

### Dictionary Properties
Dictionaries are **ordered** (since Python 3.7), **changeable** (can modify, add, or remove items), and **disallow duplicate keys** (later values overwrite earlier ones).

**Example Code**:
```python
thisdict = {"brand": "Ford", "model": "Mustang", "year": 1964, "year": 2020}
print(thisdict)  # Outputs: {'brand': 'Ford', 'model': 'Mustang', 'year': 2020}
print(len(thisdict))  # Outputs: 3
```
- **Explanation**:
  - `{"brand": "Ford", "model": "Mustang", "year": 1964, "year": 2020}`: Duplicate key `"year"` results in the last value (`2020`). **Output**: `{'brand': 'Ford', 'model': 'Mustang', 'year': 2020}`.
  - `len(thisdict)`: Counts key-value pairs. **Output**: `3`.
- **Common Mistake**: Expecting duplicate keys to be preserved.
  - **Fix**: Use unique keys or store multiple values in a list, e.g., `"years": [1964, 2020]`.

### Dictionary Items - Data Types
Dictionary values can be any data type, including strings, integers, booleans, lists, or even other dictionaries.

**Example Code**:
```python
thisdict = {"brand": "Ford", "electric": False, "year": 1964, "colors": ["red", "white", "blue"]}
print(thisdict)  # Outputs: {'brand': 'Ford', 'electric': False, 'year': 1964, 'colors': ['red', 'white', 'blue']}
```
- **Explanation**: Stores mixed types (string, boolean, integer, list). **Output**: Shows all key-value pairs.
- **Common Mistake**: Using unhashable types like lists as keys, e.g., `{["key"]: "value"}`.
  - **Error**: `TypeError`.
  - **Fix**: Use immutable types like strings or tuples for keys, e.g., `{("key",): "value"}`.

### Accessing Dictionary Items
Access items using keys in square brackets `[]`, the `get()` method, or methods like `keys()`, `values()`, and `items()`. Check key existence with `in`.

**Example Code**:
```python
thisdict = {"brand": "Ford", "model": "Mustang", "year": 1964}
print(thisdict["model"])  # Outputs: Mustang
print(thisdict.get("model"))  # Outputs: Mustang
print(thisdict.keys())  # Outputs: dict_keys(['brand', 'model', 'year'])
print(thisdict.values())  # Outputs: dict_values(['Ford', 'Mustang', 1964])
print(thisdict.items())  # Outputs: dict_items([('brand', 'Ford'), ('model', 'Mustang'), ('year', 1964)])
print("model" in thisdict)  # Outputs: True
```
- **Explanation**:
  - `thisdict["model"]`: Accesses value for key `"model"`. **Output**: `Mustang`.
  - `get("model")`: Same as above. **Output**: `Mustang`.
  - `keys()`: Returns a view of keys. **Output**: `dict_keys(['brand', 'model', 'year'])`.
  - `values()`: Returns a view of values. **Output**: `dict_values(['Ford', 'Mustang', 1964])`.
  - `items()`: Returns a view of key-value tuples. **Output**: `dict_items([('brand', 'Ford'), ('model', 'Mustang'), ('year', 1964)])`.
  - `"model" in thisdict`: Checks key presence. **Output**: `True`.
- **Common Mistake**: Accessing non-existent key with `[]`, e.g., `thisdict["color"]`.
  - **Error**: `KeyError`.
  - **Fix**: Use `get()` (returns `None` if key missing) or check with `in`.

### Changing Dictionary Items
Change values using key assignment or the `update()` method.

**Example Code**:
```python
thisdict = {"brand": "Ford", "model": "Mustang", "year": 1964}
thisdict["year"] = 2018  # Change value
print(thisdict)  # Outputs: {'brand': 'Ford', 'model': 'Mustang', 'year': 2018}
thisdict.update({"model": "Focus"})  # Update value
print(thisdict)  # Outputs: {'brand': 'Ford', 'model': 'Focus', 'year': 2018}
```
- **Explanation**:
  - `thisdict["year"] = 2018`: Updates `"year"`. **Output**: `{'brand': 'Ford', 'model': 'Mustang', 'year': 2018}`.
  - `update({"model": "Focus"})`: Updates `"model"`. **Output**: `{'brand': 'Ford', 'model': 'Focus', 'year': 2018}`.
- **Common Mistake**: Using `update()` with invalid argument, e.g., `update("model", "Focus")`.
  - **Error**: `TypeError`.
  - **Fix**: Use dictionary or key-value pairs, e.g., `update({"model": "Focus"})`.

### Adding Dictionary Items
Add items using new keys or `update()`.

**Example Code**:
```python
thisdict = {"brand": "Ford", "model": "Mustang", "year": 1964}
thisdict["color"] = "red"  # Add item
print(thisdict)  # Outputs: {'brand': 'Ford', 'model': 'Mustang', 'year': 1964, 'color': 'red'}
thisdict.update({"type": "coupe"})  # Add item
print(thisdict)  # Outputs: {'brand': 'Ford', 'model': 'Mustang', 'year': 1964, 'color': 'red', 'type': 'coupe'}
```
- **Explanation**:
  - `thisdict["color"] = "red"`: Adds new key-value pair. **Output**: Includes `color`.
  - `update({"type": "coupe"})`: Adds new key-value pair. **Output**: Includes `type`.
- **Common Mistake**: Adding duplicate keys overwrites existing values.
  - **Fix**: Check with `in` before adding.

### Removing Dictionary Items
Use `pop()`, `popitem()`, `del`, or `clear()` to remove items.

**Example Code**:
```python
thisdict = {"brand": "Ford", "model": "Mustang", "year": 1964}
thisdict.pop("model")  # Remove specific key
print(thisdict)  # Outputs: {'brand': 'Ford', 'year': 1964}
thisdict.popitem()  # Remove last item
print(thisdict)  # Outputs: {'brand': 'Ford'}
thisdict.clear()  # Empty dictionary
print(thisdict)  # Outputs: {}
```
- **Explanation**:
  - `pop("model")`: Removes `"model"`. **Output**: `{'brand': 'Ford', 'year': 1964}`.
  - `popitem()`: Removes last inserted item (Python 3.7+). **Output**: `{'brand': 'Ford'}`.
  - `clear()`: Empties dictionary. **Output**: `{}`.
- **Common Mistake**: Using `pop()` on non-existent key, e.g., `thisdict.pop("color")`.
  - **Error**: `KeyError`.
  - **Fix**: Use `pop("color", None)` or check with `in`.

### Looping Through Dictionaries
Loop through keys, values, or key-value pairs using `for`, `keys()`, `values()`, or `items()`.

**Example Code**:
```python
thisdict = {"brand": "Ford", "model": "Mustang", "year": 1964}
for x in thisdict:  # Loop keys
    print(x)  # Outputs: brand, model, year
for x in thisdict.values():  # Loop values
    print(x)  # Outputs: Ford, Mustang, 1964
for x, y in thisdict.items():  # Loop key-value pairs
    print(x, y)  # Outputs: brand Ford, model Mustang, year 1964
```
- **Explanation**:
  - `for x in thisdict`: Iterates over keys. **Output**: `brand`, `model`, `year`.
  - `for x in thisdict.values()`: Iterates over values. **Output**: `Ford`, `Mustang`, `1964`.
  - `for x, y in thisdict.items()`: Iterates over key-value tuples. **Output**: `brand Ford`, `model Mustang`, `year 1964`.
- **Common Mistake**: Expecting `for x in thisdict` to yield values.
  - **Fix**: Use `thisdict.values()` for values.

### Copying Dictionaries
Use `copy()` or `dict()` to create independent copies, as direct assignment creates a reference.

**Example Code**:
```python
thisdict = {"brand": "Ford", "model": "Mustang", "year": 1964}
mydict = thisdict.copy()  # Copy dictionary
print(mydict)  # Outputs: {'brand': 'Ford', 'model': 'Mustang', 'year': 1964}
mydict2 = dict(thisdict)  # Copy using dict()
print(mydict2)  # Same output
```
- **Explanation**:
  - `copy()`: Creates a new dictionary. **Output**: `{'brand': 'Ford', 'model': 'Mustang', 'year': 1964}`.
  - `dict(thisdict)`: Same as above.
- **Common Mistake**: Using `mydict = thisdict`, which creates a reference.
  - **Error**: Changes to `mydict` affect `thisdict`.
  - **Fix**: Use `copy()` or `dict()`.

### Nested Dictionaries
Dictionaries can contain other dictionaries for hierarchical data.

**Example Code**:
```python
myfamily = {
    "child1": {"name": "Emil", "year": 2004},
    "child2": {"name": "Tobias", "year": 2007},
    "child3": {"name": "Linus", "year": 2011}
}
print(myfamily["child2"]["name"])  # Outputs: Tobias
for x, obj in myfamily.items():  # Loop nested dictionary
    print(x)
    for y in obj:
        print(y + ':', obj[y])
```
- **Explanation**:
  - `myfamily`: Nested dictionary with three sub-dictionaries. **Output**: None. **Side Effects**: Stores nested structure.
  - `myfamily["child2"]["name"]`: Accesses nested value. **Output**: `Tobias`.
  - Nested loop: Prints keys and sub-dictionary key-value pairs. **Output**: `child1`, `name: Emil`, `year: 2004`, etc.
- **Common Mistake**: Accessing non-existent nested key, e.g., `myfamily["child4"]["name"]`.
  - **Error**: `KeyError`.
  - **Fix**: Check with `in` or use `get()`.

**One-Line Takeaway**: Python dictionaries store ordered, changeable key-value pairs with no duplicate keys, supporting access, modification, looping, copying, and nesting.

---

## Section 2 — Class Exercise

### Exercise: Car Dictionary Explorer

**Objective**: Write a Python program that manipulates a dictionary of car details using access, add, remove, and loop operations.

**Step-by-Step Instructions**:
1. Create a file named `car_dict.py`.
2. Declare a dictionary `car` (e.g., `{"brand": "Ford", "model": "Mustang", "year": 1964}`).
3. Perform and print:
   - Value of `"model"` using `get()`.
   - List of keys using `keys()`.
   - Add `"color": "red"` using assignment.
   - Change `"year"` to `2020` using `update()`.
   - Remove `"model"` using `pop()`.
   - Check if `"brand"` exists using `in`.
   - Loop through key-value pairs using `items()`.
4. Add comments to explain each step.
5. Run with `python car_dict.py`.

**Hints**:
- Use `get()` to avoid errors with non-existent keys.
- Use `update()` for dictionary-based updates.
- Order of items is preserved (Python 3.7+).

**Checkpoint**:
- Verify output shows correct manipulations and loop results.
- Ensure `"brand" in car` returns `True`.

**Example Output** (for `car = {"brand": "Ford", "model": "Mustang", "year": 1964}`):
```
Car Dictionary:
Model: Mustang
Keys: dict_keys(['brand', 'model', 'year'])
After adding color: {'brand': 'Ford', 'model': 'Mustang', 'year': 1964, 'color': 'red'}
After updating year: {'brand': 'Ford', 'model': 'Mustang', 'year': 2020, 'color': 'red'}
After removing model: {'brand': 'Ford', 'year': 2020, 'color': 'red'}
Is brand in dictionary? True
Car Details:
brand: Ford
year: 2020
color: red
```

---

## Section 3 — Weekly Project

### Project: Family Dictionary Manager

**Objective**: Create a Python program that manages a nested dictionary of family members, using access, modification, and looping.

**Milestones**:
1. Create a file named `family_dict.py`.
2. Declare a nested dictionary `myfamily` (e.g., `{"child1": {"name": "Emil", "year": 2004}, ...}`).
3. Perform:
   - Print the name of `child2` using nested access.
   - Print all keys of `myfamily` using `keys()`.
   - Add `"hobby": "reading"` to `child1` using `update()`.
   - Change `child3`’s year to `2015` using key assignment.
   - Remove `child2`’s year using `pop()`.
   - Create a copy of `myfamily` using `copy()`.
   - Check if `"child1"` exists using `in`.
   - Loop through `myfamily` to print all keys and nested key-value pairs.
   - Validate `myfamily` is a dictionary using `isinstance()`.
4. Print results with f-strings and comments.
5. Run with `python family_dict.py`.

**Deliverables**:
- A working `family_dict.py` file.
- Output showing all operations and validations.

**Research Prompts**:
- Why are dictionaries ordered in Python 3.7+, and how does this affect their use?
- How do nested dictionaries improve data organization in real-world applications?

**Assessment Criteria**:
- Code runs without errors.
- Dictionary manipulations (access, add, remove) are correct.
- Nested dictionary access and looping work.
- Output is clear and commented.
- Copy and type validation function correctly.

**Extension Idea**:
- Add a new child dictionary using `update()`.
- Extract all names into a list using a loop or list comprehension.

**Example Output** (for specified `myfamily`):
```
Family Dictionary:
Child2 name: Tobias
Keys: dict_keys(['child1', 'child2', 'child3'])
After adding hobby to child1: {'child1': {'name': 'Emil', 'year': 2004, 'hobby': 'reading'}, ...}
After updating child3 year: {'child1': {...}, 'child2': {...}, 'child3': {'name': 'Linus', 'year': 2015}}
After removing child2 year: {'child1': {...}, 'child2': {'name': 'Tobias'}, 'child3': {...}}
Copy of family: {'child1': {...}, 'child2': {'name': 'Tobias'}, 'child3': {...}}
Is child1 in dictionary? True
Is myfamily a dictionary? True
Family Details:
child1
name: Emil
year: 2004
hobby: reading
child2
name: Tobias
child3
name: Linus
year: 2015
```

---

## Completion Checklist
- [ ] Understood dictionary creation with `{}` and `dict()`.
- [ ] Accessed items using `[]`, `get()`, `keys()`, `values()`, `items()`.
- [ ] Modified items with assignment and `update()`.
- [ ] Removed items with `pop()`, `popitem()`, `clear()`.
- [ ] Looped through dictionaries and handled nested dictionaries.
- [ ] Created copies with `copy()` or `dict()`.
- [ ] Completed the class exercise and verified the output.
- [ ] Started the weekly project and planned the family dictionary manager.
- [ ] Fixed at least one common mistake (e.g., accessing non-existent key).