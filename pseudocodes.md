# Turning Pseudo-codes into python code
### Quiz 1
```py
# Code definition of function
def Makes10(a, b):
    if a+b==10 or a==10 or b==10:
        return True
    return False
# Tests
print(Makes10(9, 10))
print(Makes10(9, 9))
print(Makes10(1, 9))
```
### Quiz 2
```py
# Code definition of function
def IntMax(a, b, c):
    if b>=a:
        if b>=c:
            max=b
        else:
            max=c
    else:
        if a>=c:
            max=a
        else:
            max=c
    return max
# Tests
print(IntMax(1, 2, 3))
print(IntMax(1, 3, 2))
print(IntMax(3, 2, 1))
```
### Quiz 3
```py
# Code definition of function
def rangeN(n):
    for i in range(0, n):
        print(i)
# Tests
print(rangeN(6))
```
### Quiz 4
```py
# Code definition of function
def perfectN(n):
    for i in range(1, n-1):
        if n%i==0:
            print(i)
# Tests
print(perfectN(6))
```
### Quiz 5 (TableM)
```py
def BigNeighbour(x):
    difference=0
    difference_max=0
    for i in range(0, len(x)-1):
        difference=abs(x[i+1]-x[i])
        if difference>difference_max:
            difference_max=difference
    return difference_max
```
### Quiz 6
```py
# Code definition of function
def MixStart(str):
    if str[1]=="i" and str[2]=="x":
        return True
    return False
# Tests
print(MixStart('mix snacks'))
print(MixStart('pix snacks'))
print(MixStart('piz snacks'))
```
### Quiz 7
```py
# Code definition of function
def SameFirstLast(x):
    if len(x)>=1 and x[0]==x[-1]:
        return True
    return False
```
### Quiz 8
```py
def wordLength(s):
    sum=0
    for i in range(0, len(s)):
        sum+=len(s[i])
    return (sum, len(s))
```
### Quiz 9
```py
def Or35(x):
    if x%5==0 or x%3==0:
        return True
    return False
```
### Quiz 10
```py
def has271(x):
    for i in range(0,len(x)-1):
        if x[i+1]==x[i]+5 and x[i+2]==x[i]-1:
            return True
    return False
```
### Quiz 11
```py
def letters(x):
    for i in range(0, len(x)+1):
        print(i,"->",x[i])
```
### Quiz 12
```py
def maxAbs(numbers):
    max=0
    for i in range(0, len(numbers)):
        if numbers[i]>max:
            max=numbers[i]
    return max
```
### Quiz 13
```py
def missingNumber(x):
    for i in range(0, len(x)-1):
        if x[i]!=x[i+1]-1:
            print(x[i]+1)
```

