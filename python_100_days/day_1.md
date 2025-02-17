# Question
> 💡 **Note :** date `02/10/2024`.

## Question 1
> Write a program which will find all such numbers which are divisible by 7 but are not a multiple of 5, 
> between 2000 and 3200(both included).
>The numbers obtained should be printed in a comma-separated sequence on a single line.*

### solution 1
```python
for i in range(2000, 3201):
    if i % 7 == 0 and  not i % 5 == 0:
        print(i, end=',')
print('\n')
```

## Question 2
> Write a program which can compute the factorial of a given numbers.The results should be printed in a comma-separated sequence on > a single 
> line. suppose the following input is supplied to the program: 8 Then, the output should be:40320.

### solution 2
```python
f = 1
n = int(input('What is the number: '))
if n == 1:
    f = 1
elif n == 2:
    f = 2
else:
    for i in range(2,(n+1)):
        f = f * i
print(f) 
```

## Question 3
> With a given integral number n, write a program to generate a dictionary that contains (i, i x i) 
> such that is an integral number between 1 and n (both included). 
> and then the program should print the dictionary.Suppose the following input is supplied to the program: 8 *

### Solution 3
```python
num = int(input('What is the number: '))
d = dict()
for i in range(1,(num+1)):
        d[i] = i*i

print(d)
```

