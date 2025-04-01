## Question 17
> A website requires the users to input username and password to register. Write a program to check the
> validity of password input by users.
> Following are the criteria for checking the password:
- At least 1 letter between [a-z]
- At least 1 number between [0-9]
- At least 1 letter between [A-Z]
- At least 1 character from [$#@]
- Minimum length of transaction password: 6
- Maximum length of transaction password: 12

> Your program should accept a sequence of comma separated passwords and will check them according to the above criteria. Passwords that > > > match the criteria are to be printed, each separated by a comma.

> Example

> If the following passwords are given as input to the program:
```
ABd1234@1,a F1#,2w3E*,2We3345
```

**The output**
```
ABd1234@1
```

### solution 1

```python
def pwd_check(pwd_str):
    special_chars = {'$', '#', '@'}
    
    return all([
        any(c.islower() for c in pwd_str),
        any(c.isupper() for c in pwd_str),
        any(c.isdigit() for c in pwd_str),
        any(c in special_chars for c in pwd_str),
        6 <= len(pwd_str) <= 12 
    ])



str_input = input('=> : \n').split(',')
output = list(filter(pwd_check, str_input))
print(','.join(output))
```

### Solution 2
```python
def is_low(x):                  # Returns True  if the string has a lowercase
    for i in x:
        if 'a'<=i and i<='z':
            return True
    return  False

def is_up(x):                   # Returns True  if the string has a uppercase
    for i in x:
        if 'A'<= i and i<='Z':
            return True
    return  False

def is_num(x):                  # Returns True  if the string has a numeric digit
    for i in x:
        if '0'<=i and i<='9':
            return True
    return  False

def is_other(x):                # Returns True if the string has any "$#@"
    for i in x:
        if i=='$' or i=='#' or i=='@':
            return True
    return False

s = input().split(',')
lst = []

for i in s:
    length = len(i)
    if 6 <= length and length <= 12 and is_low(i) and is_up(i) and is_num(i) and is_other(i):   #Checks if all the requirments are fulfilled
        lst.append(i)

print(",".join(lst))
```

### Solution 3
```python
import  re

s = input().split(',')
lst = []

for i in s:
    cnt = 0
    cnt+=(6<=len(i) and len(i)<=12)
    cnt+=bool(re.search("[a-z]",i))      # here re module includes a function re.search() which returns the object information
    cnt+=bool(re.search("[A-Z]",i))      # of where the pattern string i is matched with any of the [a-z]/[A-z]/[0=9]/[@#$] characters
    cnt+=bool(re.search("[0-9]",i))      # if not a single match found then returns NONE which converts to False in boolean
    cnt+=bool(re.search("[@#$]",i))      # expression otherwise True if found any.
    if cnt == 5:
        lst.append(i)

print(",".join(lst))
```