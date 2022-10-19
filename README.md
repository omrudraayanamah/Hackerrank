# Hackerrank challenge
## Algorithms
####Between Two Sets
    def getTotalX(a, b):
    countx=0
    lst=[]
    for j in range(arr[0],brr[m-1]+1,arr[0]):
        X=True
        for i in range(0,len(arr)):
            D=bool(j%arr[i]==0)
            X = X and D
        if X is True:
            lst.append(j)    
    for j in range(0,len(lst)):  
        X=True
        for i in range(0,len(brr)):
            D=bool(brr[i]%lst[j]==0)
            X = X and D
        if X is True:
            countx=countx+1
    return countx
####Number Line Jumps
    def kangaroo(x1, v1, x2, v2):
        # Write your code here
        Ans=''
        if x1>x2 and v1<v2:
            X=x1-x2
            V=v2-v1
            if X%V==0:
                Ans='Yes'
            else:
                Ans='No'
        elif x1<x2 and v1>v2:
            X=x2-x1
            V=v1-v2
            if X%V==0:
                Ans='Yes'
            else:
                Ans='No'
        else:
            Ans='No'
        return Ans
#### Apple and Orange
    def countApplesAndOranges(s, t, a, b, apples, oranges):
    # Write your code here
    for i in range(0,m):
        apples[i]=apples[i]+a
    for i in range(0,n):
        oranges[i]=oranges[i]+b
    count=0
    countx=0
    for i in range(0,m):
        if s<=apples[i]<=t:
            count=count+1
    for i in range(0,n):
        if s<=oranges[i]<=t:
            countx=countx+1
    print(count)
    print(countx)
#### Grading Students
    def gradingStudents(grades):
        for i in range(0,len(grades)):
            if grades[i]>35:
                if grades[i]%5>=3:
                    grades[i]=grades[i]+5-grades[i]%5

        return grades
#### Maximum Perimeter Triangle
    def maximumPerimeterTriangle(sticks):
        ##Total possible pair 
        x=0
        lst=[]
        for i in range(0,n):
            for j in range(0,n):
                for k in range(0,n):
                    if i!=j and j!=k and k!=i:
                        lst.append([sticks[i],sticks[j],sticks[k]])


        try:
            ## Triangle condition                
            tri=[]
            for i in range(0,len(lst)):
                if lst[i][0]+lst[i][1]>lst[i][2] and lst[i][1]+lst[i][2]>lst[i][0] and lst[i][2]+lst[i][0]>lst[i][1]:
                    tri.append(lst[i])

            ## Maximum perimeter
            mx=0
            list3=[]
            for i in range(0,len(tri)):
                if sum(tri[i])>mx:
                    mx=sum(tri[i])
            for i in range(0,len(tri)):
                if sum(tri[i])==mx:
                    list3.append(tri[i])

            a=max(list3)
            a.sort()

            print(a[0],end=' ')
            print(a[1],end=' ')
            print(a[2],end=' ')
        except:
            return [-1]
#### Luck Balance
    def luckBalance(k, contests):
        l=0
        lst=[]
        negative_num=0
        contests.sort()
        for i in range(0,n):
            if contests[i][1]==0:
                l=l+contests[i][0]
            else:
                lst.append(contests[i][0])

        for i in range(0,len(lst)):
            if i<len(lst)-k:
                negative_num=negative_num+lst[i]
            else:
                l=l+lst[i]

        return l-negative_num

#### Grid Challenge
        def gridChallenge(grid):
    z0=''
    y= True
    l=len(grid[0])
    for j in range(0,l):
        for i in range(0,n):
            z0 = z0 + ''.join(sorted(grid[i]))[j]

        ans0=''.join(sorted(z0))

        x=bool(z0==ans0)

        y= y and x
        z0=''
    if y==True:
        ans='YES'
    else:
        ans='NO'
    return ans

#### Marc's Cakewalk
        def marcsCakewalk(calorie):
    x=0
    calorie.sort(reverse=True)
    for i in range(0,n):
        x=x+2**i*calorie[i]
    return x
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
