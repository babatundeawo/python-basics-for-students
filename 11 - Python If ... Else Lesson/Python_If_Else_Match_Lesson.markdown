# **Python If ... Else and Match Statements: Nigeria-Focused Beginner’s Guide**

This guide follows the **AI Instructional Framework for Teaching Python Beginners (Nigeria-Focused Edition)**, providing a comprehensive, beginner-friendly explanation of Python’s conditional statements (`if`, `elif`, `else`, logical operators, nested `if`, `pass`, and `match`) with Nigerian-themed examples, exercises, and a project. The response is structured into three sections: **Explanations**, **Class Exercise**, and **Weekly Project**.

---

## **Section 1 – Explanations**

This section explains the concepts of Python conditions, `if` statements, logical operators, nested `if`, the `pass` statement, and the `match` statement, as outlined in the lesson note. Each concept is broken down step-by-step, tied to Nigerian experiences, and includes clear examples.

### **1. Python Conditions**
Python uses conditions to make decisions, like choosing whether to buy airtime or data based on your budget. The conditions are:
- **Equals (`==`)**: Checks if two values are the same, e.g., `a == b`.
- **Not Equals (`!=`)**: Checks if two values are different, e.g., `a != b`.
- **Less than (`<`)**: Checks if one value is smaller, e.g., `a < b`.
- **Less than or equal to (`<=`)**: Checks if one value is smaller or equal, e.g., `a <= b`.
- **Greater than (`>`)**: Checks if one value is larger, e.g., `a > b`.
- **Greater than or equal to (`>=`)**: Checks if one value is larger or equal, e.g., `a >= b`.

**Relatable Analogy**: Think of conditions like deciding whether to board a danfo bus. If the fare is less than or equal to the money in your pocket (`fare <= money`), you can board. If not, you walk or wait for a cheaper bus.

### **2. If Statements**
An `if` statement checks a condition and runs code if the condition is true. It’s like deciding to buy *suya* only if you have enough money.

**Example from Lesson**:
```python
a = 33
b = 200
if b > a:
  print("b is greater than a")
```
**Line-by-Line Explanation**:
- `a = 33`: Stores the number 33 in a variable called `a`, like writing your WAEC score on a slip.
- `b = 200`: Stores 200 in a variable called `b`.
- `if b > a:`: Checks if `b` (200) is greater than `a` (33). Since 200 is indeed greater, the condition is true.
- `print("b is greater than a")`: Prints the message because the condition is true.
- **Output**: `b is greater than a`.

**Relatable Example**:
Imagine you’re checking if you can afford a ₦200 recharge card:
```python
money = 150
recharge_cost = 200
if money >= recharge_cost:
    print("You can buy the recharge card!")
```
Here, since 150 is less than 200, the message won’t print. This is like checking your pocket before buying airtime at a market.

### **3. Indentation**
Python uses indentation (spaces at the start of a line) to group code under an `if` statement. Without proper indentation, Python raises an error, like a teacher rejecting a poorly written essay.

**Example from Lesson (Error Case)**:
```python
a = 33
b = 200
if b > a:
print("b is greater than a") # Error: no indentation
```
- The `print` statement must be indented (usually 2 or 4 spaces) under the `if` to show it belongs to the `if` block. Without indentation, Python doesn’t know it’s part of the `if`.

**Corrected Example**:
```python
a = 33
b = 200
if b > a:
    print("b is greater than a") # Properly indented
```
- **Output**: `b is greater than a`.

**Relatable Analogy**: Indentation is like arranging your JAMB answer sheet neatly under each question number so the examiner knows which answers belong to which question.

### **4. Elif**
The `elif` keyword checks another condition if the previous `if` or `elif` conditions are false. It’s like choosing between MTN, Glo, or Airtel based on which has the cheapest data plan.

**Example from Lesson**:
```python
a = 33
b = 33
if b > a:
    print("b is greater than a")
elif a == b:
    print("a and b are equal")
```
**Line-by-Line Explanation**:
- `a = 33` and `b = 33`: Both variables store 33.
- `if b > a:`: Checks if 33 > 33. This is false, so the `print` inside is skipped.
- `elif a == b:`: Checks if 33 == 33. This is true, so the next line runs.
- `print("a and b are equal")`: Prints the message.
- **Output**: `a and b are equal`.

**Relatable Example**:
Checking if you have enough money for a school fee:
```python
money = 5000
fee = 5000
if money > fee:
    print("You can pay the fee and have change!")
elif money == fee:
    print("You can pay the fee exactly!")
```
- If `money` equals `fee` (5000 == 5000), it prints: `You can pay the fee exactly!`.

### **5. Else**
The `else` keyword runs code when all previous `if` and `elif` conditions are false. It’s like saying, “If I can’t buy data or airtime, I’ll just send a ‘Please Call Me’ message.”

**Example from Lesson**:
```python
a = 200
b = 33
if b > a:
    print("b is greater than a")
elif a == b:
    print("a and b are equal")
else:
    print("a is greater than b")
```
**Line-by-Line Explanation**:
- `a = 200` and `b = 33`: Variables store 200 and 33.
- `if b > a:`: Checks if 33 > 200. False, so skip.
- `elif a == b:`: Checks if 200 == 33. False, so skip.
- `else:`: Since all previous conditions are false, run the `else` block.
- `print("a is greater than b")`: Prints the message.
- **Output**: `a is greater than b`.

**Relatable Example**:
```python
age = 15
if age >= 18:
    print("You can vote in the election!")
else:
    print("You are too young to vote.")
```
- If `age` is 15, it prints: `You are too young to vote.`

### **6. Short Hand If and If-Else**
A **short-hand `if`** puts a single statement on the same line as the `if`. A **short-hand `if-else`** (ternary operator) handles both `if` and `else` in one line.

**Short-Hand If Example**:
```python
a = 200
b = 33
if a > b: print("a is greater than b")
```
- If 200 > 33, it prints: `a is greater than b`.

**Short-Hand If-Else Example**:
```python
a = 2
b = 330
print("A") if a > b else print("B")
```
- Since 2 is not greater than 330, it prints: `B`.

**Short-Hand with Multiple Conditions**:
```python
a = 330
b = 330
print("A") if a > b else print("=") if a == b else print("B")
```
- Since 330 == 330, it prints: `=`.

**Relatable Example**:
```python
score = 75
print("Pass") if score >= 50 else print("Fail")
```
- If your exam score is 75, it prints: `Pass`. This is like checking if you passed a WAEC subject.

### **7. Logical Operators: And, Or, Not**
Logical operators combine conditions:
- **And**: Both conditions must be true.
- **Or**: At least one condition must be true.
- **Not**: Reverses the condition’s result.

**And Example**:
```python
a = 200
b = 33
c = 500
if a > b and c > a:
    print("Both conditions are True")
```
- Checks if 200 > 33 (true) and 500 > 200 (true). Since both are true, it prints: `Both conditions are True`.

**Or Example**:
```python
a = 200
b = 33
c = 500
if a > b or a > c:
    print("At least one of the conditions is True")
```
- Checks if 200 > 33 (true) or 200 > 500 (false). Since one is true, it prints: `At least one of the conditions is True`.

**Not Example**:
```python
a = 33
b = 200
if not a > b:
    print("a is NOT greater than b")
```
- `a > b` (33 > 200) is false. `not` makes it true, so it prints: `a is NOT greater than b`.

**Relatable Example**:
```python
money = 1000
data_cost = 500
airtime_cost = 200
if money >= data_cost and money >= airtime_cost:
    print("You can buy both data and airtime!")
```
- If you have ₦1000, you can afford both ₦500 data and ₦200 airtime, so it prints the message.

### **8. Nested If**
A nested `if` is an `if` statement inside another `if`. It’s like checking if you have enough money for a bus fare, then checking if the bus is going to your destination.

**Example from Lesson**:
```python
x = 41
if x > 10:
    print("Above ten,")
    if x > 20:
        print("and also above 20!")
    else:
        print("but not above 20.")
```
**Line-by-Line Explanation**:
- `x = 41`: Stores 41.
- `if x > 10:`: 41 > 10 is true, so print: `Above ten,`.
- `if x > 20:`: 41 > 20 is true, so print: `and also above 20!`.
- **Output**:
  ```
  Above ten,
  and also above 20!
  ```

**Relatable Example**:
```python
age = 16
if age >= 15:
    print("You can register for WAEC.")
    if age >= 16:
        print("You can also take the exam this year!")
    else:
        print("But you need to wait till next year.")
```
- For `age = 16`, it prints both messages because both conditions are true.

### **9. The Pass Statement**
The `pass` statement is a placeholder when you want an `if` block to do nothing, avoiding errors.

**Example from Lesson**:
```python
a = 33
b = 200
if b > a:
    pass
```
- Since `b > a` is true, but `pass` does nothing, no output is produced.

**Relatable Example**:
```python
score = 60
if score >= 50:
    pass  # You passed, but we’ll print nothing for now.
```
- This is like a teacher noting you passed an exam but not announcing it yet.

### **10. Python Match Statement**
The `match` statement is a cleaner way to handle multiple conditions, like choosing what to do based on the day of the week.

**Example from Lesson**:
```python
day = 4
match day:
    case 1:
        print("Monday")
    case 2:
        print("Tuesday")
    case 3:
        print("Wednesday")
    case 4:
        print("Thursday")
    case 5:
        print("Friday")
    case 6:
        print("Saturday")
    case 7:
        print("Sunday")
```
- `day = 4` matches `case 4`, so it prints: `Thursday`.

**Default Value Example**:
```python
day = 4
match day:
    case 6:
        print("Today is Saturday")
    case 7:
        print("Today is Sunday")
    case _:
        print("Looking forward to the Weekend")
```
- Since `day = 4` doesn’t match 6 or 7, the `_` case runs, printing: `Looking forward to the Weekend`.

**Combine Values Example**:
```python
day = 4
match day:
    case 1 | 2 | 3 | 4 | 5:
        print("Today is a weekday")
    case 6 | 7:
        print("I love weekends!")
```
- `day = 4` matches the first case, so it prints: `Today is a weekday`.

**If Statements as Guards Example**:
```python
month = 5
day = 4
match day:
    case 1 | 2 | 3 | 4 | 5 if month == 4:
        print("A weekday in April")
    case 1 | 2 | 3 | 4 | 5 if month == 5:
        print("A weekday in May")
    case _:
        print("No match")
```
- `day = 4` and `month = 5` match the second case, so it prints: `A weekday in May`.

**Relatable Example**:
```python
market_day = 3
match market_day:
    case 1:
        print("Go to Oyingbo Market.")
    case 2:
        print("Go to Mile 12 Market.")
    case 3:
        print("Go to Balogun Market.")
    case _:
        print("No market today, rest!")
```
- For `market_day = 3`, it prints: `Go to Balogun Market.` This is like choosing which Lagos market to visit based on the day.

---

## **Section 2 – Class Exercise**

**Exercise: Build a “JAMB Score Checker”**

This exercise uses `if`, `elif`, `else`, and logical operators to check a student’s JAMB score and determine their admission status. It’s fun, relatable, and something students can show off to friends.

**Instructions**:
1. Ask the user to input their JAMB score (a number between 0 and 400).
2. Store the score in a variable.
3. Use `if`, `elif`, and `else` to check:
   - If the score is 200 or above, print: “Great job! You’re eligible for university admission.”
   - If the score is between 150 and 199, print: “Good effort! You’re eligible for polytechnic admission.”
   - If the score is below 150, print: “Try again next year.”
4. Add a logical operator (`and`) to check if the score is valid (between 0 and 400). If invalid, print: “Invalid score! JAMB scores are between 0 and 400.”
5. Do **not** write the full code. Guide the student step-by-step.

**Step-by-Step Guidance**:
- Use `input()` to get the score and convert it to an integer with `int()`.
- Use an `if` statement with `and` to check if the score is between 0 and 400.
- Inside the valid score check, use `if`, `elif`, and `else` to evaluate the score ranges.
- Test with scores like 250, 180, 100, and 450 to see different outputs.
- Ensure proper indentation for all `print` statements.

**Why It’s Fun**: Students can share this with friends, saying, “I built a program that checks JAMB results like a real system!”

---

## **Section 3 – Weekly Project**

**Project: Danfo Bus Fare and Seat Availability Checker**

This project combines `if`, `elif`, `else`, logical operators, and the `match` statement to create a program that calculates bus fares and checks seat availability for danfo bus routes in Lagos. It’s practical, exciting, and something students can proudly show off.

**Project Brief**:
Create a program that:
1. Asks the user to input a danfo route (e.g., 1 for “Oshodi to CMS”, 2 for “Yaba to Obalende”, 3 for “Ikeja to Agege”).
2. Uses a `match` statement to assign the fare based on the route.
3. Asks the user how many seats are available in the bus (a number).
4. Uses `if`, `elif`, and `else` with logical operators to check:
   - If seats are available and the user has enough money, print the fare and a confirmation.
   - If seats are unavailable, print a message to wait for another bus.
   - If the user doesn’t have enough money, print a message to top up.
5. Add a validity check for the route and seat input.

**Milestones**:
1. **Input Collection**:
   - Use `input()` to get the route number (1, 2, or 3) and convert to an integer.
   - Use `input()` to get the number of available seats and the user’s money.
2. **Route and Fare Assignment**:
   - Use a `match` statement to set fares: Oshodi to CMS (₦300), Yaba to Obalende (₦200), Ikeja to Agege (₦150).
   - Use `_` as a default case for invalid routes.
3. **Seat and Money Check**:
   - Use `if` with `and` to check if seats > 0 and money >= fare.
   - Use `elif` for cases where seats are 0 or money is insufficient.
   - Use `else` for invalid inputs (e.g., negative seats).
4. **Output**:
   - Print messages like: “Your fare for Oshodi to CMS is ₦300. Seat confirmed!” or “No seats available, wait for another bus.”

**Example Interaction**:
```
Enter route (1=Oshodi-CMS, 2=Yaba-Obalende, 3=Ikeja-Agege): 1
Enter available seats: 2
Enter your money (₦): 500
Your fare for Oshodi to CMS is ₦300. Seat confirmed!
```

**Extensions**:
- Add a student discount (e.g., 10% off if the user is a student).
- Suggest alternative routes if no seats are available.

**Why It’s Exciting**: Students can show friends a program that feels like a real Lagos danfo ticketing system, sparking conversations like, “I coded a bus fare checker with Python!”