# Solution to the Greeting Function Exercise

## Explanation

The exercise asks you to create a function called `greet_customer` that takes a customer’s first name and an optional order item (with a default value of `"coffee"`) to print a personalized greeting for a coffee shop. The function should be called twice: once with just a name and once with both a name and an order item. Additionally, you should test using a keyword argument for the order and consider what happens if the `name` argument is omitted.

### Key Concepts Used
- **Functions**: We define a function using the `def` keyword to create reusable code.
- **Parameters and Default Parameters**: The function accepts a required parameter (`name`) and an optional parameter (`order`) with a default value.
- **String Concatenation**: We combine strings to create a personalized message.
- **Function Calls**: We call the function with different combinations of arguments to test its behavior.
- **Error Handling**: Omitting a required argument like `name` will cause an error, demonstrating the importance of matching the number of arguments.

### Solution Approach
1. Define the `greet_customer` function with `name` as a required parameter and `order` with a default value of `"coffee"`.
2. Inside the function, use string concatenation to print a greeting like `"Hello, [name]! Enjoy your [order]!"`.
3. Call the function:
   - First with only a name (e.g., `"Alice"`) to use the default `order`.
   - Second with both a name and an order (e.g., `"Bob", "tea"`).
4. Test with a keyword argument for `order` (e.g., `order="juice"`).
5. Demonstrate what happens if `name` is omitted (this will raise an error).

### Solution Code
Below is the complete solution with the function definition and test calls:

```python
def greet_customer(name, order="coffee"):
    print("Hello, " + name + "! Enjoy your " + order + "!")

# Test 1: Call with just a name
greet_customer("Alice")  # Output: Hello, Alice! Enjoy your coffee!

# Test 2: Call with name and order
greet_customer("Bob", "tea")  # Output: Hello, Bob! Enjoy your tea!

# Test 3: Call with keyword argument for order
greet_customer("Charlie", order="juice")  # Output: Hello, Charlie! Enjoy your juice!

# Test 4: What happens if name is omitted? (This will raise an error)
# greet_customer()  # Error: missing 1 required positional argument: 'name'
```

### Explanation of the Code
- **Function Definition**: `def greet_customer(name, order="coffee")` creates a function with `name` as a required parameter and `order` with a default value of `"coffee"`. If no `order` is provided, it defaults to `"coffee"`.
- **Printing the Greeting**: The `print` statement concatenates strings to form the message. For example, `greet_customer("Alice")` produces `"Hello, Alice! Enjoy your coffee!"`.
- **Test Calls**:
  - `greet_customer("Alice")`: Uses the default `order` value, printing `"Hello, Alice! Enjoy your coffee!"`.
  - `greet_customer("Bob", "tea")`: Provides both arguments, printing `"Hello, Bob! Enjoy your tea!"`.
  - `greet_customer("Charlie", order="juice")`: Uses a keyword argument for `order`, printing `"Hello, Charlie! Enjoy your juice!"`.
- **Error Case**: If you call `greet_customer()` without a `name`, Python raises a `TypeError` because `name` is a required positional argument. This is commented out in the code to avoid execution errors but is included to show the consequence.
- **Default Parameter Benefit**: The default value for `order` ensures the function works even if only a name is provided, making it flexible for common cases (e.g., most customers order coffee).

### Discussion Point
If you forget the `name` argument, Python will raise an error: `TypeError: greet_customer() missing 1 required positional argument: 'name'`. This highlights the importance of providing all required arguments. The default parameter for `order` helps by allowing the function to work without specifying an order, assuming a common choice like `"coffee"`. This is useful in real-world scenarios where you want to simplify function calls for frequent cases.

This solution builds confidence by using simple string manipulation and function calls while reinforcing the importance of proper argument handling for beginners.