# Turning Pseudo-codes into python code
### Quiz 1
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
### Quiz 2
```py
def SameFirstLast(x):
    if len(x)>=1 and x[0]==x[-1]:
        return True
    return False
```
### Quiz 3
```py
def wordLength(s):
    sum=0
    for i in range(0, len(s)):
        sum+=len(s[i])
    return (sum, len(s))
```
### Quiz 4
```py
def Or35(x):
    if x%5==0 or x%3==0:
        return True
    return False
```
### Quiz 5
```py
def Makes10(a, b):
    if a+b==10 or a==10 or b==10:
        return True
    return False
```
### Quiz 6
```py
def has271(x):
    for i in range(0,len(x)-1):
        if x[i+1]==x[i]+5 and x[i+2]==x[i]-1:
            return True
    return False
```
### Quiz 7
```py
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
```
### Quiz 8
```py
def rangeN(n):
    for i in range(0, n):
        print(i)
```
### Quiz 9
```py
def perfectN(n):
    for i in range(1, n-1):
        if n%i==0:
            print(i)
```
### Quiz 10
```py
def MixStart(str):
    if str[1]=="i" and str[2]=="x":
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

