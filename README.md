# Python
# Hackerrank challenge
## Algorithms
### Warmup

1. Simple Array Sum

def simpleArraySum(ar):
    # Write your code here
    x=0
    for i in range(0,ar_count):
        x=x+ar[i]
    return x

2. Compare the Triplets

def compareTriplets(a, b):
    # Write your code here
    x=0
    y=0
    if a[0]>b[0]:
        x= 1
    elif a[0]<b[0]:
        y=1
    if a[1]>b[1]:
        x=x+1
    elif a[1]<b[1]:
        y=y+1
    if a[2]>b[2]:
        x=x+1
    elif a[2]<b[2]:
        y=y+1
    return x,y
    
3. Diagonal Difference

def diagonalDifference(arr):
    # Write your code here
    x=0
    for i in range(0,n):
        x=x+arr[i][i]
    y=0
    for i in range(0,n):
        y=y+arr[i][(n-1)-i]
    return abs(x-y)

4. Plus Minus

def plusMinus(arr):
    # Write your code here
    x=0
    y=0
    z=0
    for i in range(0,n):
        if arr[i]>0:
            x=x+1
        elif arr[i]==0:
            y=y+1
        else:
            z=z+1
    print('%.6f' % (x/n))
    print('%.6f' % (z/n))
    print('%.6f' % (y/n))
