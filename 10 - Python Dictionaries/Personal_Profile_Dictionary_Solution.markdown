# Solution to Personal Profile Dictionary Exercise

## Explanation

The exercise asks you to create a program that stores information about a person in a dictionary, performs operations like accessing, adding, and checking for keys, and displays the results. Below is a step-by-step explanation of the solution, tailored for complete beginners, with clear connections to the dictionary concepts from the lesson.

### Step-by-Step Breakdown
1. **Creating the Dictionary**:
   - We create a dictionary called `person` with three key:value pairs: `"name"`, `"age"`, and `"hobby"`. This uses the curly bracket syntax `{}` from the lesson.
   - Example values: `"Emma"` (string), `25` (integer), and `"Reading"` (string).

2. **Accessing the "name" Key**:
   - We use the `get()` method to safely access the value of the `"name"` key, as it avoids errors if the key doesn’t exist (though in this case, we know it does). The lesson showed both square brackets and `get()` as valid methods.

3. **Adding a "city" Key**:
   - We add a new key `"city"` with the value `"New York"` using the `update()` method, as shown in the lesson. This demonstrates how to add new key:value pairs to an existing dictionary.

4. **Checking if "hobby" Exists**:
   - We use the `in` keyword to check if `"hobby"` is a key in the dictionary, as demonstrated in the lesson’s “Check if Key Exists” section. If it exists, we print a confirmation message.

5. **Printing the Entire Dictionary**:
   - We print the dictionary to show all key:value pairs, including the newly added `"city"`, to confirm the changes.

### Solution Code
Below is the complete Python code that solves the exercise, followed by the expected output.

```python
# Step 1: Create a dictionary with name, age, and hobby
person = {
    "name": "Emma",
    "age": 25,
    "hobby": "Reading"
}

# Step 2: Print the value of the "name" key using get()
print(person.get("name"))

# Step 3: Add a new key "city" with value "New York"
person.update({"city": "New York"})

# Step 4: Check if "hobby" exists in the dictionary
if "hobby" in person:
    print("Hobby is included!")

# Step 5: Print the entire dictionary
print(person)
```

### Expected Output
```
Emma
Hobby is included!
{'name': 'Emma', 'age': 25, 'hobby': 'Reading', 'city': 'New York'}
```

### Why This Works
- **Dictionary Creation**: The dictionary `person` is initialized with the required keys, following the lesson’s syntax.
- **Accessing Values**: Using `get("name")` retrieves `"Emma"`, aligning with the lesson’s example of accessing values.
- **Adding Items**: The `update()` method adds `"city": "New York"`, as shown in the lesson’s “Add Dictionary Items” section.
- **Checking Keys**: The `in` keyword checks for `"hobby"`, matching the lesson’s example of key existence checking.
- **Displaying Results**: Printing the dictionary shows all key:value pairs, confirming the addition of the new key.

This solution is beginner-friendly, uses only the concepts from the lesson, and demonstrates practical dictionary operations in a clear, confidence-building way.