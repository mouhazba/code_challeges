## Question 10
> Write a program that accepts a sequence of whitespace separated words as input and prints the words after removing 
> all duplicate words and sorting them alphanumerically.

> Suppose the following input is supplied to the program:
```
hello world and practice makes perfect and hello world again
```

**The output**
```
again and hello makes perfect practice world
```

### solution 1

```python
inputs = input('=> : ').split(' ')

outputs = []
for w in inputs:
    if w not in outputs:
        outputs.append(w)
print(' '.join(sorted(outputs)))
```

### solution 2  

```python
word = input('=> : ').split()

for i in word:
    if word.count(i) > 1:
        word.remove(i)     

word.sort()
print(" ".join(word))
```

### solution 3

```python
inputs = input('=> : ').split(' ')

outputs = set(inputs)

print(' '.join(sorted(outputs)))
```
## Question 11:
> Write a program which accepts a sequence of comma separated 4 digit binary numbers as its input and then check whether
they are divisible by 5 or not. The numbers that are divisible by 5 are to be printed in a comma separated sequence.
> Example:
```
0100,0011,1010,1001
```
> Then the output should be:
```
1010
```
### solution 1
```python
def BinToDecimal(n):
    return int(n,2)

def even5(n):
    return  (BinToDecimal(n) % 5 == 0)

inpust = input('=> : ').split(',')
outputs = list(filter(even5,inpust))

print('.'.join(outputs))
```

### solution 2
```python
def BinToDecimal(n):
    return int(n,2)

def even5(n):
    return  (BinToDecimal(n) % 5 == 0)

inpust = input('=> : ').split(',')
outputs = list(filter(lambda n: int(n,2) % 5 == 0,inpust))

print('.'.join(outputs))
```
### Solution 3

```python
print(*(binary for binary in input().split(',') if int(binary,base=2)%5==0))
```

## Question 12
> Write a program, which will find all such numbers between 1000 and 3000 (both included) such that each digit of the number is an even 
> number. The numbers obtained should be printed in a comma-separated sequence on a single line.

### Solution 1
```python
inpust = list(range(1000, 3000))
outputs = list(filter(lambda n: n % 2 == 0,inpust))
outputs = list(map(str,outputs))
print(','.join(outputs))
```

### Solution 2
```python
'''
genere un sequence filtree sans liste intermediaire:
*(expression for element in iterable if condition)
'''
print(*(binary for binary in input('=> : ').split(',') if int(binary,base=2)%5==0))

```

## Question 13
> Write a program that accepts a sentence and calculate the number of letters and digits.

> Suppose the following input is supplied to the program:
```
hello world! 123
```

> then output should be:
```
LETTERS 10
DIGITS 3
```
### Solution 1
```python
inputs = input('=> : ?')
i = 0
j = 0
for c in inputs:
    if c.isalpha():
        i += 1

    elif c.isdigit():
        j += 1


print(f'LETTERS {i}'.strip())
print(f'DIGITS {j}'.strip())

```

### Solution 2
```python
from collections import Counter

inputs = input('=> : ?\n')
counts = Counter(inputs)

letters = sum(counts[c] for c in counts if c.isalpha())
digits = sum(counts[c] for c in counts if c.isdigit())

print(f'LETTERS {letters}')
print(f'DIGITS {digits}')

```

### solution 3
```python
inputs = input('=> : ?')

letters = len(list(filter(str.isalpha, inputs)))
digits = len(list(filter(str.isdigit, inputs)))

print(f'LETTERS {letters}')
print(f'DIGITS {digits}')
```




