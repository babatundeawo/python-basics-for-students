# **Solution to the Danfo Bus Passenger Tracker Project (Nigeria-Focused Edition)**

This document provides the code solution to the **Danfo Bus Passenger Tracker** weekly project from the Python Dictionaries lesson, along with a detailed explanation tailored for Nigerian beginners. The solution adheres to the Nigeria-focused instructional framework, ensuring it is clear, relatable, beginner-friendly, and something students can proudly share with peers. The explanation follows the same structure as the original lesson response, focusing on the project's concepts and code.

---

## **Section 1 – Explanations**

This section explains the solution to the **Danfo Bus Passenger Tracker** project, breaking down the code step-by-step with Nigerian-themed examples. The project involves creating a program that:
1. Stores passenger details (name and destination) in a nested dictionary.
2. Uses a separate dictionary for fares based on destination.
3. Allows the user to add a new passenger or check a passenger’s fare.
4. Displays the total number of passengers and their details.

### **Solution Code**
Below is the complete Python code for the Danfo Bus Passenger Tracker:

```python
# Dictionary for fares based on destination
fares = {
    "CMS": 200,
    "Ojota": 150,
    "Ikeja": 100
}

# Nested dictionary for passenger details
passengers = {}

# Main program loop
while True:
    print("\nDanfo Bus Passenger Tracker")
    print("1. Add a new passenger")
    print("2. Check passenger fare")
    print("3. Show all passengers")
    print("4. Exit")
    
    choice = input("Enter your choice (1-4): ")
    
    if choice == "1":
        # Add a new passenger
        passenger_id = input("Enter passenger ID (e.g., passenger1): ")
        name = input("Enter passenger name: ")
        destination = input("Enter destination (CMS, Ojota, Ikeja): ")
        
        # Store passenger details in nested dictionary
        passengers[passenger_id] = {
            "name": name,
            "destination": destination
        }
        print(f"Passenger {name} added successfully!")
    
    elif choice == "2":
        # Check passenger fare
        passenger_id = input("Enter passenger ID to check fare: ")
        if passenger_id in passengers:
            destination = passengers[passenger_id]["destination"]
            fare = fares.get(destination, "Unknown destination")
            if fare != "Unknown destination":
                print(f"Name: {passengers[passenger_id]['name']}, Destination: {destination}, Fare: ₦{fare}")
            else:
                print(f"Error: Destination {destination} not found in fare list.")
        else:
            print("Passenger not found.")
    
    elif choice == "3":
        # Show all passengers
        if passengers:
            print(f"\nTotal passengers: {len(passengers)}")
            print("Passenger Details:")
            for passenger_id, details in passengers.items():
                print(f"{passenger_id}: Name: {details['name']}, Destination: {details['destination']}")
        else:
            print("No passengers recorded.")
    
    elif choice == "4":
        print("Exiting Danfo Bus Passenger Tracker. Safe travels!")
        break
    
    else:
        print("Invalid choice. Please select 1, 2, 3, or 4.")
```

### **Line-by-Line Explanation**

This code uses nested dictionaries, loops, conditionals, `input()`, and string formatting, all tailored to a Nigerian danfo bus context. It’s interactive and mimics a real tool a bus driver in Lagos might use. Below is a detailed breakdown:

1. **Creating the Fares Dictionary**:
   ```python
   fares = {
       "CMS": 200,
       "Ojota": 150,
       "Ikeja": 100
   }
   ```
   - Creates a dictionary `fares` with destinations as keys and fares in naira as values.
   - **Relatable Analogy**: This is like a danfo driver’s fare chart for routes in Lagos, where each destination has a fixed price.

2. **Creating the Passengers Dictionary**:
   ```python
   passengers = {}
   ```
   - Initializes an empty nested dictionary to store passenger details.
   - Each passenger will have a unique ID (e.g., `"passenger1"`) as the key, and their value will be another dictionary with `"name"` and `"destination"`.
   - **Relatable Analogy**: This is like the driver’s passenger logbook, where each passenger’s details are recorded.

3. **Main Program Loop**:
   ```python
   while True:
       print("\nDanfo Bus Passenger Tracker")
       print("1. Add a new passenger")
       print("2. Check passenger fare")
       print("3. Show all passengers")
       print("4. Exit")
       choice = input("Enter your choice (1-4): ")
   ```
   - Uses a `while True` loop to keep the program running until the user chooses to exit.
   - Displays a menu with four options and gets the user’s choice using `input()`.
   - **Relatable Analogy**: This is like the driver offering options to manage passengers, similar to how a conductor interacts with passengers on a danfo bus.

4. **Option 1: Add a New Passenger**:
   ```python
   if choice == "1":
       passenger_id = input("Enter passenger ID (e.g., passenger1): ")
       name = input("Enter passenger name: ")
       destination = input("Enter destination (CMS, Ojota, Ikeja): ")
       passengers[passenger_id] = {
           "name": name,
           "destination": destination
       }
       print(f"Passenger {name} added successfully!")
   ```
   - Asks for a passenger ID, name, and destination using `input()`.
   - Creates a nested dictionary for the passenger and adds it to `passengers`.
   - Confirms the addition with a message.
   - **Relatable Analogy**: This is like the conductor noting down a new passenger’s details when they board the bus at Oshodi.

5. **Option 2: Check Passenger Fare**:
   ```python
   elif choice == "2":
       passenger_id = input("Enter passenger ID to check fare: ")
       if passenger_id in passengers:
           destination = passengers[passenger_id]["destination"]
           fare = fares.get(destination, "Unknown destination")
           if fare != "Unknown destination":
               print(f"Name: {passengers[passenger_id]['name']}, Destination: {destination}, Fare: ₦{fare}")
           else:
               print(f"Error: Destination {destination} not found in fare list.")
       else:
           print("Passenger not found.")
   ```
   - Asks for a passenger ID and checks if it exists in `passengers` using `in`.
   - Retrieves the passenger’s destination from the nested dictionary.
   - Uses `fares.get(destination, "Unknown destination")` to safely get the fare, returning a default message if the destination isn’t in `fares`.
   - Prints the passenger’s name, destination, and fare, or an error if the passenger or destination isn’t found.
   - **Relatable Analogy**: This is like the conductor checking a passenger’s destination and telling them the fare, ensuring they don’t charge for an unknown route.

6. **Option 3: Show All Passengers**:
   ```python
   elif choice == "3":
       if passengers:
           print(f"\nTotal passengers: {len(passengers)}")
           print("Passenger Details:")
           for passenger_id, details in passengers.items():
               print(f"{passenger_id}: Name: {details['name']}, Destination: {details['destination']}")
       else:
           print("No passengers recorded.")
   ```
   - Checks if `passengers` is not empty using `if passengers`.
   - Uses `len(passengers)` to count passengers.
   - Loops through `passengers` using `items()` to print each passenger’s ID, name, and destination.
   - If no passengers are recorded, prints a message.
   - **Relatable Analogy**: This is like the driver reviewing their passenger list at the end of a trip to see who’s on board.

7. **Option 4: Exit**:
   ```python
   elif choice == "4":
       print("Exiting Danfo Bus Passenger Tracker. Safe travels!")
       break
   ```
   - Exits the loop with `break`, ending the program.
   - Prints a friendly message.
   - **Relatable Analogy**: This is like the driver closing their logbook and ending the day’s work.

8. **Invalid Choice**:
   ```python
   else:
       print("Invalid choice. Please select 1, 2, 3, or 4.")
   ```
   - Handles invalid inputs by prompting the user to choose a valid option.
   - **Relatable Analogy**: This is like the conductor correcting a passenger who gives unclear instructions.

### **Why It’s Beginner-Friendly**
- The code uses familiar concepts: dictionaries (nested and regular), `input()`, conditionals (`if-elif-else`), loops (`while`, `for`), and string formatting.
- The menu-driven structure is intuitive, like choosing options on a mobile app.
- The Nigerian danfo bus context makes it relatable, as students can imagine a real Lagos bus driver using this tool.

### **Confidence-Building**
- Students can run this program and see it work like a real passenger tracker, which they can proudly show to friends, saying, “I built a program for a danfo driver to track passengers!”
- The program combines multiple concepts into a practical tool, showing how Python can solve everyday problems in Nigeria.

### **Sample Output**
```
Danfo Bus Passenger Tracker
1. Add a new passenger
2. Check passenger fare
3. Show all passengers
4. Exit
Enter your choice (1-4): 1
Enter passenger ID (e.g., passenger1): passenger1
Enter passenger name: Amina
Enter destination (CMS, Ojota, Ikeja): CMS
Passenger Amina added successfully!

Danfo Bus Passenger Tracker
1. Add a new passenger
2. Check passenger fare
3. Show all passengers
4. Exit
Enter your choice (1-4): 2
Enter passenger ID to check fare: passenger1
Name: Amina, Destination: CMS, Fare: ₦200

Danfo Bus Passenger Tracker
1. Add a new passenger
2. Check passenger fare
3. Show all passengers
4. Exit
Enter your choice (1-4): 3
Total passengers: 1
Passenger Details:
passenger1: Name: Amina, Destination: CMS

Danfo Bus Passenger Tracker
1. Add a new passenger
2. Check passenger fare
3. Show all passengers
4. Exit
Enter your choice (1-4): 4
Exiting Danfo Bus Passenger Tracker. Safe travels!
```

**Alternative Scenario (Error Handling)**:
```
Danfo Bus Passenger Tracker
1. Add a new passenger
2. Check passenger fare
3. Show all passengers
4. Exit
Enter your choice (1-4): 2
Enter passenger ID to check fare: passenger2
Passenger not found.

Danfo Bus Passenger Tracker
1. Add a new passenger
2. Check passenger fare
3. Show all passengers
4. Exit
Enter your choice (1-4): 5
Invalid choice. Please select 1, 2, 3, or 4.
```

---

This solution and explanation cover the Danfo Bus Passenger Tracker project comprehensively, using a Nigerian context to make it engaging and relatable. The program is practical, fun, and something students can boast about, as it mimics a real tool for a Lagos bus driver. Let me know if you need further clarification or additional features!