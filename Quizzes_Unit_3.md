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
        f = 0
        if i in food:
            total += prices[p] * 1.1
            f = 1
        if i in electronics:
            total += prices[p] * 1.15
            f = 1
        if i in liqueur:
            total += prices[p] * 1.2
            f = 1
        elif f == 0:
            print("{} is not in the database".format(i))
            print("Add it to food(type 1), electronics(type 2) or liqueur(type 3)? : ")
            respond = int(input())
            if respond == 1:
                food.append(i)
                print("{} has been added to food database:{}".format(i,food))
            if respond == 2:
                electronics.append(i)
                print("{} has been added to electronics database:{}".format(i, electronics))
            if respond == 3:
                liqueur.append(i)
                print("{} has been added to liqueur database:{}".format(i, liqueur))


    return total
print(total(["bread","beer","ipad"], [300, 800, 30000]))
print(total(["cake","laptop","wine"], [200, 55000, 3000]))
print(total(["whiskey","smartphone","iphone"], [5000, 200, 36000]))

```
### Result:
![photo](https://github.com/TimurGar/Unit-3/blob/main/Quiz%2013%20result.png)
