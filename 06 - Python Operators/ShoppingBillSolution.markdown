# Solution to the Shopping Bill Exercise

## Explanation

The exercise requires calculating the total cost of two grocery items, applying a 10% discount, and checking if a given budget is sufficient to cover the discounted total. The solution uses Python's arithmetic operators (`+` for addition, `*` for multiplication) and comparison operators (`>=` to check if the budget is enough). The steps are broken down to ensure clarity for beginners, and the code is simple to build confidence. Below is the solution with explanations for each step.

### Step-by-Step Breakdown
1. **Define Variables**: Create variables for the prices of two items and a budget. For example, `item1_price = 25`, `item2_price = 15`, and `budget = 35`.
2. **Calculate Total Cost**: Use the `+` operator to add the prices of the two items.
3. **Apply 10% Discount**: Multiply the total cost by `0.9` (since a 10% discount means paying 90% of the original price).
4. **Check Budget**: Use the `>=` operator to compare the discounted total with the budget and determine if the budget is sufficient.
5. **Print Results**: Display the total cost, discounted total, and whether the budget is enough using `print()` statements.

This solution reinforces the use of arithmetic and comparison operators from the lesson while keeping the problem practical and relatable.

## Solution Code

```python
# Step 1: Define prices and budget
item1_price = 25
item2_price = 15
budget = 35

# Step 2: Calculate total cost
total_cost = item1_price + item2_price

# Step 3: Apply 10% discount (multiply by 0.9)
discounted_total = total_cost * 0.9

# Step 4: Check if budget is enough
can_afford = budget >= discounted_total

# Step 5: Print results
print("Total cost before discount: $", total_cost)
print("Total cost after 10% discount: $", discounted_total)
print("Can you afford it with $", budget, "? ", can_afford)
```

## Output Explanation
When you run the code:
- `total_cost` is `25 + 15 = 40`.
- `discounted_total` is `40 * 0.9 = 36`.
- `can_afford` checks if `35 >= 36`, which is `False` (the budget is not enough).
- The output will be:
  ```
  Total cost before discount: $ 40
  Total cost after 10% discount: $ 36.0
  Can you afford it with $ 35 ? False
  ```

This solution is beginner-friendly, uses only the operators introduced in the lesson, and applies them to a real-world scenario of shopping and budgeting.