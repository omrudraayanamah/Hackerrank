# Hackerrank challenge
## Algorithms





#### Marc's Cakewalk

#### Time Conversion
    def timeConversion(s):
    v=None
    ans=''
    x=s[0]+s[1]
    x=int(x)
    if s[8]=='A':
        if x==12:
            v='00'
        elif x<10:
            v='0'+str(x)
        else:
            v=str(x)
    else:
        if x<12:
            v=str(x+12)
        else:
            v=str(x)
            
    ans=''
    for i in range(2,8):
        ans=ans+s[i]
    return v+ans
    
#### Birthday Cake Candles

def birthdayCakeCandles(candles):
    # Write your code here
    mx=0
    for i in range(0,candles_count):
        if candles[i]>mx:
            mx=candles[i]
    return candles.count(mx)

#### Simple Array Sum

def simpleArraySum(ar):
    # Write your code here
    x=0
    for i in range(0,ar_count):
        x=x+ar[i]
    return x

#### Compare the Triplets

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
    
#### Diagonal Difference

def diagonalDifference(arr):
    # Write your code here
    x=0
    for i in range(0,n):
        x=x+arr[i][i]
    y=0
    for i in range(0,n):
        y=y+arr[i][(n-1)-i]
    return abs(x-y)

#### Plus Minus
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

#### Staircase
def staircase(n):
    # Write your code here
    k=1
    for j in range(0,n):
        for i in range(0,n):
            if i>=n-1:
                x='#'*k
                print(x)
                k=k+1
            else:
                print(' ',end='')
        n=n-1

#### Mini-Max Sum
def miniMaxSum(arr):
    # Write your code here
    mx=arr[0]
    mnx=arr[0]
    x=0
    n=len(arr)
    for i in range(0,n):
        if arr[i]>mx:
            mx=arr[i]
        if arr[i]<mnx:
            mnx=arr[i]
        x=x+arr[i]
    return print(x-mx, x-mnx)
