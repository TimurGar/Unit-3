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
            total += prices[p] * 1.1
        if i in electronics:
            total += prices[p] * 1.15
        if i in liqueur:
            total += prices[p] * 1.2

    return total
print(total(["bread","beer","ipad"], [300, 800, 30000]))
print(total(["apple","laptop","wine"], [200, 55000, 3000]))
print(total(["whiskey","orange","iphone"], [5000, 200, 36000]))

```
### Result:
![photo](https://github.com/TimurGar/Unit-3/blob/main/Result%20to%20Quiz%2013.png)
