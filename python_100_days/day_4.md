## Question 14
> Write a program that accepts a sentence and calculate the number of upper case letters and lower case letters.
> all duplicate words and sorting them alphanumerically.

> Suppose the following input is supplied to the program:
```
Hello world!
```

**The output**
```
UPPER CASE 1
LOWER CASE 9
```

### solution 1

```python
inputs = input('=> : ? ').split(',')

square_odd = [str(int(i)**2 ) for i in inputs if int(i) % 2 != 0]
print(",".join(square_odd))
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



