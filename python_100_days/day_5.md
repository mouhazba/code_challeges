## Question 15
> Use a list comprehension to square each odd number in a list. The list is input by a sequence of comma-separated numbers.
> Suppose the following input is supplied to the program:

> Suppose the following input is supplied to the program:
```
1,2,3,4,5,6,7,8,9
```

**The output**
```
1,9,25,49,81
```

### solution 1

```python
inputs = input(" => : ?")

total_low = 0
total_upper = 0
for c in inputs:
    total_low += c.islower()
    total_upper += c.isupper()

print(f'UPPER CASE {total_upper}')
print(f'LOWER CASE {total_low}')

```

### solution 2  

```python
inputs = input(" => : ?")

print(f'LOWER CASE : {sum(map(lambda x: x.islower(), inputs))}')
print(f'UPPER CASE : {sum(map(lambda x: x.isupper(), inputs))}')
```

### solution 3

```python
inputs = input(" => : ?")

print(f'LOWER CASE : {len(list(filter(lambda x: x.islower(), inputs)))}')
print(f'UPPER CASE : {len(list(filter(lambda x: x.isupper(), inputs)))}')
```
### solution 4
```python
inputs = input(" => : ?")

print(f'LOWER CASE : {sum(1 for c in inputs if c.islower())}')
print(f'UPPER CASE : {sum(1 for c in inputs if c.isupper())}')
```

## Question 16
> Write a program that computes the net amount of a bank account based a transaction log from console input. 
> The transaction log format is shown as following:

```
D 100
W 200
```
- D means deposit while W means withdrawal.

> Suppose the following input is supplied to the program:

```
D 300
D 300
W 200
D 100
```

> Then, the output should be:

```
500
```

### Solution 1
```python
d = []
w = []
while True:
    inpt = input('=> : ?\n')
    if inpt == 'q':
        break
    type_dep, dep = inpt.split(' ')
    if type_dep == 'D':
        d.append(dep)
    elif type_dep == 'W':
        w.append(dep)

print(sum(int(i) for i in d) - sum(int(i) for i in w))
```