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

## Quiz 18
### Solution
```.py
# Quiz 18

class Quiz18():
    # Initializing the class:
    def __init__(self,N):
        self.N = N

    # Creating an algorithm that is going to calculate the number of steps needed
    def num_steps(self):
        steps = 0
        while len(self.N) > 1:
            p = 1
            steps += 1
            for i in range(len(self.N)):
                p *= int(self.N[i])
                
            self.N = str(p)

        return steps

test1 = Quiz18("39").num_steps()
print(test1)
```
### Testing
![](https://github.com/TimurGar/Unit-3/blob/main/Quizzes%20uni3/Quiz%2018.png)


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
### Testing
![](https://github.com/TimurGar/Unit-3/blob/main/Quizzes%20uni3/Quiz%2019%20test.png)
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
### Testing
![](https://github.com/TimurGar/Unit-3/blob/main/Quizzes%20uni3/Quiz%2020%20test.png)


## Quiz 21
### Solution
```.py
# Quiz 21
# Inputs:
# face of the emoji, left hand

# Output:
# full emoji(left hand, face, right hand)


#######Notes#######
# Input (~n~), <-
# <.../ \...>

# normal diff 2(<>,{},[])

# / - 47
# \ - 92
# dif 45

# ( - 40
# ) - 41
# dif 1
#######Notes#######

class Quiz_21():
    # initialyzing
    def __init__(self,face,larm):
        self.face = face
        self.larm = larm

    # algorithm that will make a full emoji
    def emoji(self):
        # flipping the hand(left to right)
        rarm = self.larm[::-1]
        out = ""
        odd_char_f = ""

        # Checking if any if the right hand,rarm, contains any irregular characters
        # Irregular characters: <>,{},[], /\
        for l in rarm:
            if l not in "-.|o\\":
                # Convertring characters to UNICODE, changing the character and converting back
                # chr - num to character, Ex: 41 - ")"
                # ord - character to num, Ex: ")" - 41
                odd_char_f += chr(ord(l) + 2)
            elif l in "\\":
                odd_char_f += chr(ord(l) - 45)
            else:
                odd_char_f += l


        rarm = rarm.replace(rarm[-1], odd_char_f)
        out = self.larm + self.face + odd_char_f

        print(out)

test1 = Quiz_21("(~n~)","|-").emoji()
test2 = Quiz_21("('|-|')","o-").emoji()
test3 = Quiz_21("[?????]","<...\\").emoji()
```
### Testing
![](https://github.com/TimurGar/Unit-3/blob/main/Quizzes%20uni3/Quiz%2021%20test.png)

## Quiz 22
### Solution
```.py
# Quiz 22
# Input:
# string, Ex: "Hello world !"

# Output:
# string with first and last character of the string and the number of characters in between,
# Ex: H3o w3d !


class Quiz_22():
    # initialyzing
    def __init__(self,inp):
        self.inp = inp

    # main algorithm
    def BlackBox(self):
        out = ""
        # spliting string into words or numbers
        sinp = self.inp.split(" ")
        for i in sinp:
            mlen = len(i)
            if mlen > 2:
                # combaning first, num in between, and last characters
                out += f"{i[0]}{mlen-2}{i[-1]} "
            else:
                out += f"{i} "
        print(out)

# Testinf
tes1 = Quiz_22("internationalization").BlackBox()
tes2 = Quiz_22("Hello world !").BlackBox()
tes3 = Quiz_22("98 99 100 101 102").BlackBox()
tes4 = Quiz_22("(codin) + (game) = (codingame)").BlackBox()

```
### Testing
![](https://github.com/TimurGar/Unit-3/blob/main/Quizzes%20uni3/Quiz%2022%20test.png)

## Quiz 23
### Solution
```.py
# Quiz 23
# Inputs:
# Three sides of the triangles

# Output:
# prints weather the input sides can construct a triangle


class Quiz_23():
    # initializing
    def __init__(self,a,b,c):
        self.a = a
        self.b = b
        self.c = c
    
    # the algorithm that will check weather the input size can construct a triangle
    def Triangles(self):
        if self.a + self.b > self.c and self.b + self.c > self.a and self.a + self.c > self.b:
            return print(True)
        else:
            return print(False)
# Testing
test1 = Quiz_23(1,1,2).Triangles()
test2 = Quiz_23(5,6,3).Triangles()
test3 = Quiz_23(1,2,9).Triangles()
test4 = Quiz_23(3,9,2).Triangles()
```
### Testing
![](https://github.com/TimurGar/Unit-3/blob/main/Quizzes%20uni3/Quiz%2023%20test.png)

## Quiz 24
### Solution
```.py
# Quiz 24
# Inputs:
# coefficients a,b,c,d

# Output:
# expanded binomial

class Quiz_24():
    # initializing
    def __init__(self,a,b,c,d):
        self.a = a
        self.b = b
        self.c = c
        self.d = d

    # An algorithm that uses FOIL method to create and expanded binomial
    def foil(self):
        first = self.a* self.c
        print_first = "" if first <= 1 else first
        second = self.a * self.d + self.b * self.c
        third = self.b * self.d
        sign = "-" if second and third < 0 else "+"

        out = f"{print_first}x^2{sign}{abs(second)}x{sign}{abs(third)}"
        print(out)

# Testing
test1 = Quiz_24(1,3,1,2).foil()
test2 = Quiz_24(1,13,1,-27).foil()
```
### Testing
![](https://github.com/TimurGar/Unit-3/blob/main/Quizzes%20uni3/Quiz%2024%20test.png)

## Quiz 25
### Solution
```.py

```
### Testing
![](https://github.com/TimurGar/Unit-3/blob/main/Quizzes%20uni3/Quiz%2024%20test.png)

## Quiz 26
### Solution
```.py
# Quiz 26
# Inputs:
# List of numbers

# Output:
# sum of numbers in the list except between numbers 6 and 7

class Quiz_26():
    # initializing
    def __init__(self,list_of_numbers):
        self.list_of_numbers = list_of_numbers

    # My original solution
    def sum67(self):
        sum = 0
        sub_numbers = 0
        # Going through every number in the list
        for index, number in enumerate(self.list_of_numbers):
            sum += number
            # if number in a list is 6
            if number == 6:
                # record the index of the number
                index6 = index
                # adding all the numbers between 6 and 7
                while self.list_of_numbers[index6] != 7:
                    sub_numbers += self.list_of_numbers[index6]
                    index6 += 1
                sub_numbers += 7
        # subtracting the sum of numbers between 6 and 7 from all the numbers
        total = sum - sub_numbers
        print(total)

    # Second solution
    def sum67_dif(self):
        flag = False
        sum = 0
        for i in range(len(self.list_of_numbers)):
            if flag == False:
                if self.list_of_numbers[i] == 6:
                    flag = True
                else:
                    sum += self.list_of_numbers[i]
            else:
                if self.list_of_numbers[i] == 7:
                    flag = False

        print(sum)

# testing
Quiz_26([1,2,2]).sum67()
Quiz_26([1,2,2,6,99,99,7]).sum67()
Quiz_26([1,1,6,7,2]).sum67()
print("Second solution: ")
Quiz_26([1,2,2]).sum67_dif()
Quiz_26([1,2,2,6,99,99,7]).sum67_dif()
Quiz_26([1,1,6,7,2]).sum67_dif()
```
### Testing
![Quiz 26](https://user-images.githubusercontent.com/60378207/113383490-019c7700-93bf-11eb-985a-3d8155e59553.png)
