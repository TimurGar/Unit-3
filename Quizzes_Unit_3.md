# Quizzes Unit-3
## Quiz 13

```.py
# Quiz 13
def total(items,prices):
    food = ["bread", "apple", "orange"]
    electronics = ["ipad", "laptop", "iphone"]
    liqueur = ["beer", "wine", "whiskey"]
    total = 0
    for p,i in enumerate(items):     # index, item
        if i in food:
            total += (prices[p] + prices[p]/10)
        if i in electronics:
            total += (prices[p] + prices[p]/15)
        if i in liqueur:
            total += (prices[p] + prices[p]/20)

    return total
print(total(["bread","beer","ipad"], [300, 800, 30000]))
print(total(["apple","laptop","wine"], [100, 45000, 3000]))
print(total(["whiskey","orange","iphone"], [5000, 200, 36000]))
```
### Result:
