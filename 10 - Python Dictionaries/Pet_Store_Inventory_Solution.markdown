# Solution to Pet Store Inventory Project

## Explanation

The **Pet Store Inventory** project requires creating a program to manage a pet store’s inventory using a dictionary with nested dictionaries for each pet. The program must allow adding a new pet, updating a pet’s price, displaying all pet details, and include a challenge to check for a specific pet type. This solution is designed for complete beginners, using only concepts from the Python dictionaries lesson (creating, accessing, modifying, looping, and nested dictionaries). Below is a step-by-step explanation of the solution, followed by the code and expected output.

### Step-by-Step Breakdown
1. **Creating the Dictionary**:
   - We create a dictionary called `pet_store` with at least three pets, each represented as a nested dictionary with keys `"type"`, `"name"`, and `"price"`. This uses the nested dictionary structure from the lesson (e.g., `myfamily` example).
   - Example: `"pet1": {"type": "Dog", "name": "Buddy", "price": 500}`.

2. **Adding a New Pet**:
   - We add a new pet (`"pet3"`) with its own nested dictionary using the `update()` method, as shown in the lesson’s “Add Dictionary Items” section. This demonstrates adding a new key:value pair where the value is another dictionary.

3. **Updating a Price**:
   - We update the price of `"pet1"` by increasing it by 50 using direct assignment (e.g., `pet_store["pet1"]["price"]`), as shown in the lesson’s “Change Dictionary Items” section for nested dictionaries.

4. **Displaying All Pets**:
   - We use a `for` loop with the `items()` method to iterate through the `pet_store` dictionary, accessing each pet’s nested dictionary and printing its details in a readable format. This uses the lesson’s “Loop Through Dictionaries” and “Access Items in Nested Dictionaries” concepts.

5. **Challenge: Checking for a Specific Pet Type**:
   - We loop through the dictionary to check if any pet has the `"type"` of `"Dog"`. If found, we print a message. This extends the lesson’s looping and nested dictionary access, encouraging exploration of conditional checks within loops.

### Solution Code
Below is the complete Python code that solves the project, including the challenge, with comments for clarity.

```python
# Step 1: Create a dictionary with three pets
pet_store = {
    "pet1": {"type": "Dog", "name": "Buddy", "price": 500},
    "pet2": {"type": "Cat", "name": "Whiskers", "price": 300},
    "pet3": {"type": "Bird", "name": "Tweety", "price": 100}
}

# Step 2: Add a new pet using update()
pet_store.update({
    "pet4": {"type": "Fish", "name": "Bubbles", "price": 50}
})

# Step 3: Update the price of pet1 by increasing it by 50
pet_store["pet1"]["price"] = pet_store["pet1"]["price"] + 50

# Step 4: Display all pets using a loop
for pet_id, details in pet_store.items():
    print(f"{pet_id}: Type = {details['type']}, Name = {details['name']}, Price = {details['price']}")

# Step 5: Challenge - Check if "Dog" exists in the inventory
for pet_id, details in pet_store.items():
    if details["type"] == "Dog":
        print("We have a Dog in stock!")
```

### Expected Output
```
pet1: Type = Dog, Name = Buddy, Price = 550
pet2: Type = Cat, Name = Whiskers, Price = 300
pet3: Type = Bird, Name = Tweety, Price = 100
pet4: Type = Fish, Name = Bubbles, Price = 50
We have a Dog in stock!
```

### Why This Works
- **Dictionary Creation**: The `pet_store` dictionary is initialized with three nested dictionaries, mirroring the lesson’s nested dictionary example (`myfamily`).
- **Adding a Pet**: The `update()` method adds `"pet4"` with a nested dictionary, consistent with the lesson’s example of adding items.
- **Updating Price**: Direct assignment to `pet_store["pet1"]["price"]` modifies the nested dictionary, as shown in the lesson’s nested dictionary access and modification.
- **Looping and Displaying**: The `for` loop with `items()` iterates through key:value pairs, and nested dictionary access (`details['type']`) retrieves values, aligning with the lesson’s looping and nested dictionary examples.
- **Challenge**: The second loop checks the `"type"` key in each nested dictionary, using a conditional (`if`) to find `"Dog"`, building on the lesson’s looping and access concepts.

### Additional Notes for Beginners
- **Testing**: Run the code step-by-step (e.g., after creating the dictionary, then after adding the new pet) to verify each part works.
- **Flexibility**: You can change pet types, names, or prices to experiment, as dictionaries are changeable.
- **Curiosity Spark**: The challenge introduces conditionals (`if`), which may be covered in future lessons, encouraging you to think about combining dictionary operations with other Python features.
- **Error Handling**: The code assumes keys exist (e.g., `"type"`). For robustness, you could add checks using `in`, as shown in the lesson, but this keeps it simple for beginners.

This solution is beginner-friendly, uses only dictionary concepts from the lesson, and applies them to a real-world scenario, fostering understanding and confidence while encouraging exploration of loops and conditionals.