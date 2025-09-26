# **Danfo Bus Fare and Seat Availability Checker: Python Code Solution and Explanation**

This document provides the complete Python code solution for the **Danfo Bus Fare and Seat Availability Checker** weekly project, along with a step-by-step explanation. The project combines `if`, `elif`, `else`, logical operators (`and`), and the `match` statement to create a program that calculates bus fares and checks seat availability for danfo bus routes in Lagos. It’s designed to be practical, exciting, and something Nigerian students can proudly share with friends.

---

## **Section 1 – Code Solution**

Below is the Python code for the Danfo Bus Fare and Seat Availability Checker. It prompts the user for a bus route, number of available seats, and their money, then uses a `match` statement to assign fares and `if` statements to validate inputs and confirm seat availability.

```python
# Get user inputs
route = int(input("Enter route (1=Oshodi-CMS, 2=Yaba-Obalende, 3=Ikeja-Agege): "))
seats = int(input("Enter available seats: "))
money = int(input("Enter your money (₦): "))

# Assign fare using match statement
fare = 0
match route:
    case 1:
        fare = 300  # Oshodi to CMS
    case 2:
        fare = 200  # Yaba to Obalende
    case 3:
        fare = 150  # Ikeja to Agege
    case _:
        print("Invalid route! Choose 1, 2, or 3.")
        exit()

# Validate seats and money
if seats >= 0 and money >= 0:
    if seats > 0 and money >= fare:
        print(f"Your fare for route {route} is ₦{fare}. Seat confirmed!")
    elif seats == 0:
        print("No seats available, wait for another bus.")
    else:
        print(f"Insufficient funds! You need ₦{fare}, but you have ₦{money}.")
else:
    print("Invalid input! Seats and money must be non-negative.")
```

---

## **Section 2 – Explanation**

This section breaks down the code line-by-line, explains the concepts used, and ties them to a Nigerian context to make it relatable for beginners. The explanation focuses on the lesson’s concepts: `if`, `elif`, `else`, logical operators (`and`), and the `match` statement.

### **Code Breakdown**

1. **Lines 2–4: Getting User Inputs**
   ```python
   route = int(input("Enter route (1=Oshodi-CMS, 2=Yaba-Obalende, 3=Ikeja-Agege): "))
   seats = int(input("Enter available seats: "))
   money = int(input("Enter your money (₦): "))
   ```
   - **What it does**: Uses `input()` to prompt the user for three inputs:
     - `route`: The bus route number (1, 2, or 3).
     - `seats`: The number of available seats.
     - `money`: The amount of money the user has (in ₦).
     - Each input is converted to an integer using `int()` for numerical comparisons.
   - **Why it’s important**: In Lagos, danfo buses have specific routes and fares, and passengers need to know if seats are available and if they can afford the fare. These inputs mimic that process.
   - **Relatable Analogy**: This is like a danfo conductor asking you, “Where you dey go?” and checking if you have enough money and if there’s space in the bus.

2. **Line 6: Initializing Fare**
   ```python
   fare = 0
   ```
   - **What it does**: Creates a variable `fare` and sets it to 0. This will store the fare based on the chosen route.
   - **Why it’s important**: We need a starting value before assigning the actual fare in the `match` statement.
   - **Relatable Analogy**: It’s like a conductor preparing to tell you the fare after you name your destination.

3. **Lines 7–14: Assigning Fare with Match Statement**
   ```python
   match route:
       case 1:
           fare = 300  # Oshodi to CMS
       case 2:
           fare = 200  # Yaba to Obalende
       case 3:
           fare = 150  # Ikeja to Agege
       case _:
           print("Invalid route! Choose 1, 2, or 3.")
           exit()
   ```
   - **What it does**: Uses a `match` statement to set the `fare` based on the `route`:
     - `case 1`: Sets `fare = 300` for Oshodi to CMS.
     - `case 2`: Sets `fare = 200` for Yaba to Obalende.
     - `case 3`: Sets `fare = 150` for Ikeja to Agege.
     - `case _`: If `route` is not 1, 2, or 3, prints an error and exits the program using `exit()`.
   - **Why it’s important**: The `match` statement is a clean way to handle multiple route options, like a conductor quickly naming the fare for your destination. The `_` case ensures invalid routes are caught.
   - **Relatable Analogy**: It’s like a conductor saying, “Oshodi to CMS na ₦300,” or “That route no dey, pick another one!”

4. **Line 16: Validating Seats and Money**
   ```python
   if seats >= 0 and money >= 0:
   ```
   - **What it does**: Uses an `if` statement with the `and` logical operator to check:
     - `seats >= 0`: Ensures the number of seats isn’t negative.
     - `money >= 0`: Ensures the money isn’t negative.
   - **Why it’s important**: Negative seats or money don’t make sense in real life, so this validates the inputs.
   - **Relatable Analogy**: It’s like a conductor checking if the bus has space and if your money is real before letting you board.

5. **Line 17: Checking Seat Availability and Sufficient Funds**
   ```python
   if seats > 0 and money >= fare:
       print(f"Your fare for route {route} is ₦{fare}. Seat confirmed!")
   ```
   - **What it does**: Inside the valid input block, checks if `seats > 0` and `money >= fare`. If both are true, prints a confirmation message using an f-string to include the route number and fare.
   - **Why it’s important**: This confirms the user can board the bus, mimicking a successful danfo trip.
   - **Relatable Analogy**: It’s like a conductor saying, “Oya, enter, your money complete, seat dey!”

6. **Line 19: Handling No Seats**
   ```python
   elif seats == 0:
       print("No seats available, wait for another bus.")
   ```
   - **What it does**: If `seats == 0`, prints a message telling the user to wait for another bus.
   - **Why it’s important**: Danfo buses often fill up, and passengers must wait if there’s no space.
   - **Relatable Analogy**: It’s like a conductor shouting, “Bus full, wait for the next one!”

7. **Line 21: Handling Insufficient Funds**
   ```python
   else:
       print(f"Insufficient funds! You need ₦{fare}, but you have ₦{money}.")
   ```
   - **What it does**: If `seats > 0` but `money < fare`, prints a message indicating the user doesn’t have enough money.
   - **Why it’s important**: This handles cases where the user can’t afford the fare, a common scenario in Lagos.
   - **Relatable Analogy**: It’s like a conductor saying, “Your money no reach, add ₦50!”

8. **Line 23: Handling Invalid Inputs**
   ```python
   else:
       print("Invalid input! Seats and money must be non-negative.")
   ```
   - **What it does**: If the first `if` condition (`seats >= 0 and money >= 0`) is false, prints an error for negative inputs.
   - **Why it’s important**: This ensures the program handles unrealistic inputs gracefully.
   - **Relatable Analogy**: It’s like a conductor rejecting a passenger who claims to have “-₦100” or “-2 seats.”

### **How It Works**
- The program asks for the route (1, 2, or 3), number of seats, and money.
- It uses a `match` statement to assign the fare or exit for invalid routes.
- It validates that seats and money are non-negative.
- It checks if seats are available and if the user has enough money, then prints the appropriate message.
- **Example Outputs**:
  - Input: `route = 1`, `seats = 2`, `money = 500` → Output: `Your fare for route 1 is ₦300. Seat confirmed!`
  - Input: `route = 2`, `seats = 0`, `money = 200` → Output: `No seats available, wait for another bus.`
  - Input: `route = 3`, `seats = 1`, `money = 100` → Output: `Insufficient funds! You need ₦150, but you have ₦100.`
  - Input: `route = 4`, `seats = 1`, `money = 300` → Output: `Invalid route! Choose 1, 2, or 3.`
  - Input: `route = 1`, `seats = -1`, `money = 300` → Output: `Invalid input! Seats and money must be non-negative.`

### **Key Concepts Used**
- **Input/Output**: `input()` for user input, `print()` for output.
- **Variables**: `route`, `seats`, `money`, and `fare` store user inputs and calculated values.
- **Conditions**: `>=`, `==`, and `and` for validation and checks.
- **Match Statement**: Assigns fares based on route numbers, with `_` for invalid cases.
- **If Statements**: `if`, `elif`, `else` to handle seat and money checks.
- **Indentation**: Proper spacing groups code blocks correctly.
- **Exit**: `exit()` stops the program for invalid routes.
- **F-Strings**: Format output messages dynamically (e.g., `₦{fare}`).

### **Why It’s Relatable and Fun**
- The program mimics a real Lagos danfo bus experience, from choosing a route to dealing with conductors and full buses.
- Students can share it with friends, saying, “I coded a danfo fare checker that works like a real ticketing system!” It’s practical and boast-worthy.
- It builds confidence by showing how Python can solve everyday Nigerian problems, like navigating public transport.

---

## **Section 3 – Notes for Beginners**
- **Error Handling**: The code assumes numeric inputs. In an advanced version, you could add `try/except` to handle non-numeric inputs (e.g., letters).
- **Indentation**: Ensure all lines under `if`, `elif`, `else`, and `match` cases are indented (4 spaces or 1 tab) to avoid errors.
- **Testing**: Try inputs like `route = 1`, `seats = 2`, `money = 300`; `route = 2`, `seats = 0`, `money = 200`; or `route = 4` to see different outputs.
- **Extension Ideas**:
  - Add a student discount: Ask if the user is a student and reduce the fare by 10%.
  - Suggest alternative routes: If seats are unavailable, recommend another route (e.g., “Try Ikeja to Agege instead”).
  - Add a rush hour surcharge: Increase fares by ₦50 during peak hours (e.g., if user inputs “morning”).
- **Pride Factor**: This program feels like a real-world tool, making it exciting to show off to peers or family, sparking conversations like, “I built a danfo bus system with Python!”

This project is a fun, practical step toward mastering Python conditionals while connecting to the vibrant Lagos transport culture!