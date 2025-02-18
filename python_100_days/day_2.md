## Question 4
> Write a program which accepts a sequence of comma-separated numbers from console and generate a list and a tuple.
> which contains every number.Suppose the following input is supplied to the program:
```
34,67,55,33,12,98
```

**The output**
 ```
 ['34', '67', '55', '33', '12', '98']
 ('34', '67', '55', '33', '12', '98')
 ```

### solution 1

```python
list_output  = input().split(',')
tuple_output =  tuple(list_output)
print(list_output)
print(tuple_output)
```

## Question 5:
> Define a class which has at least two methods:
> - getString: to get a string from console input
> - printString: to print the string in upper case.
> Also please include simple test function to test the class methods.

### solution 1
```python
class MyInputOutputStr:

    def getString(self):
        self.str_x = input('type a string: => ')
    
    def printStr(self):
        print(self.str_x.upper()) if self.str_x else print('None')

mystr = MyInputOutputStr()
mystr.getString()
mystr.printStr()
```

## Question 6
> Write a program that calculates and prints the value according to the given formula:
> Q = Square root of [(2 _ C _ D)/H]
> Following are the fixed values of C and H:
> C is 50. H is 30.
> D is the variable whose values should be input to your program in a comma-separated sequence.
> For example Let us assume the following comma separated input sequence is given to the program:
```
 100,150,180
 18,22,24
 ```

### solution 1
```python
from math import sqrt
C = 50
H = 30

def formula_ctdh():
    str_to_int = list(map(int, input('Type : => ').split(',')))
    cal = [round(sqrt(((2*C*D)/H))) for D in str_to_int]
    rsult = [str(i) for i in cal]
    print(','.join(rsult))

formula_ctdh()
```

### solution 2
```python
from math import sqrt
C = 50
H = 30
def cal(D):
    D = int(D)
    return str(round(sqrt((2*C*D)/H)))

x = input('Type : => ').split(',')
rsult = list(map(cal, x))
print(','.join(rsult))
```

### solution 3
```python
from math import sqrt
C = 50
H = 30
x = input('Type : => ').split(',')
rsp = list(map(lambda D: str(round(sqrt(2*C*int(D)/H))), x))

print(','.join(rsp))
```

## Question 7
> Write a program that accepts a comma separated sequence of words as input and prints 
> the words in a comma-separated sequence after sorting them alphabetically.

> Suppose the following input is supplied to the program:

```
without,hello,bag,world
```

> then output should be:
```
bag,hello,without,world
```
### Solution 1

```python
inputs = input('=> : ').split(',')
print(','.join(sorted(inputs)))
```

## Question 8
> Write a program that accepts sequence of lines as input and prints 
> the lines after making all characters in the sentence capitalized.

> Suppose the following input is supplied to the program:
```
Hello world
Practice makes perfect
```

> Then, the output should be:
```
HELLO WORLD
RACTICE MAKES PERFECT
```
### Solution 1:
```python
list_lines = []
while True:
    line = inputs = input('=> : \n')
    if not line:
        break
    list_lines.append(line.upper())

for line in list_lines:
    print(line)
```

### Solution 2
```python
import os
with open('lines.txt', 'w') as fp:
    while True:
        line = input('=> : \n')
        if not line:
            break
        fp.write(f'{line.upper()}\n')

print('---'*25)
with open('lines.txt', 'r') as f:
    while line:= f.readline():
        print(line.strip())

if os.path.exists('lines.txt'):
    os.remove('lines.txt')
```

### Solution 3
```python
from pathlib import Path
file = Path("lines.txt")

with file.open('w') as fp:
    while True:
        line = input('=> : \n')
        if not line:
            break
        fp.write(f'{line.upper()}\n')

print('---'*25)
with file.open('r') as f:
    while line:= f.readline():
        print(line.strip())

if file.exists():
    file.unlink('lines.txt')
```