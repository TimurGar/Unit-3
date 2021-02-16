# Quizzes Unit 3
## Quiz 17
### Solution No. 1
```.py
# Quiz 17
def evenly_spaced(a,b,c):
    lnum = [a,b,c]
    sorted_lnum = []

    for i in range(len(lnum)):
        max = lnum[-1]
        for i in lnum:
            if i > max:
                max = i
        sorted_lnum.append(max)
        lnum.remove(max)

    if sorted_lnum[0] - sorted_lnum[1] == sorted_lnum[1] - sorted_lnum[2]:
        return True
    else:
        return False

print(evenly_spaced(2, 4, 6))
print(evenly_spaced(4, 6, 2))
print(evenly_spaced(4, 6, 3))
```
![](https://github.com/TimurGar/Unit-3/blob/main/Quizzes%20uni3/Quiz%2017%201.png)

### Solution No. 2
```.py
class ES():
    def __init__(self,a,b,c):
        self.a: int = a
        self.b: int = b
        self.c: int = c

    def evenly_spaced(self,a,b,c):
        lnum = [a, b, c]
        sorted_lnum = []

        for i in range(len(lnum)):
            max = lnum[-1]
            for i in lnum:
                if i > max:
                    max = i
            sorted_lnum.append(max)
            lnum.remove(max)

        if sorted_lnum[0] - sorted_lnum[1] == sorted_lnum[1] - sorted_lnum[2]:
            return print(True)
        else:
            return print(False)

test1 = ES(2, 4, 6)
test2 = ES(4, 6, 2)
test3 = ES(4, 6, 3)
test1.evenly_spaced(2, 4, 6)
test2.evenly_spaced(4, 6, 2)
test3.evenly_spaced(4, 6, 3)
```
![](https://github.com/TimurGar/Unit-3/blob/main/Quizzes%20uni3/Quiz%2017%202.png)
