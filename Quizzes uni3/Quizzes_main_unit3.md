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



## Quiz 19
### Solution
```.py
# Quiz 19

Blist = ['000', '001', '010', '011', '100', '101', '110', '111']
numbers = [0,1,2,3,4,5,6,7,8,9]
class Quiz19():
    # Initializing the class:
    def __init__(self, I):
        self.I = I.split("!")

    # Creating an algorithm that is going to decode the input
    def decode(self):
        out = ""
        for i in range(len(self.I)):
            for y in range(len(Blist)):
                if self.I[i] == Blist[y]:
                    out += str(numbers[y])

        return out

test1 = Quiz19("100!000!111").decode()
print(test1)
```
## Testing
![](https://github.com/TimurGar/Unit-3/blob/main/Quizzes%20uni3/Quiz%2020%20system%20diagram.png)

## Quiz 20
### System diagram
![](https://github.com/TimurGar/Unit-3/blob/main/Quizzes%20uni3/Quiz%2020%20system%20diagram.png)
### Solution
```.py
# Quiz 20

class Quiz20():
    # Initializing the class:
    def __init__(self, inp):
        self.inp = inp

    # Creating an algorithm that is going to change the characters places
    def swap(self):

        # if the input is consist only of 1 number
        if len(self.inp) < 2:
            out = self.inp
        else:
            # if the input is bigger than 2 characters
            out = ""
            for i in range(0, len(self.inp), 2):
                out += self.inp[i+1] + self.inp[i]
        print(out)

test1 = Quiz20("01ABxy").swap()
```
