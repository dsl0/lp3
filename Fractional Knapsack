
def fractional_knapsack(capacity, items):
    # Sort items by profit/weight ratio
    items.sort(key=lambda x: x[1] / x[0], reverse=True)

    total_profit = 0

    for weight, profit in items:
        if capacity >= weight:
            capacity -= weight
            total_profit += profit

        else:
            fraction = capacity / weight
            total_profit += profit * fraction
            capacity = 0
            break

    return total_profit


n = int(input("Enter number of items: "))

items = []

for i in range(n):
    weight = int(input("Enter weight: "))
    profit = int(input("Enter profit: "))
    items.append((weight, profit))

capacity = int(input("Enter knapsack capacity: "))

result = fractional_knapsack(capacity, items)

print("Maximum Profit:", result)
