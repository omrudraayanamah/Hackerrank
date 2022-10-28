# Hackerrank challenge
## Algorithms
#### Cat and mouse
    def catAndMouse(x, y, z):
    if abs(z-x) > abs(z-y):
        ans = 'Cat B'
    elif abs(z-x) == abs(z-y):
        ans = 'Mouse C'
    else:
        ans = 'Cat A'
    return ans
#### Electronics Shop
    def getMoneySpent(keyboards, drives, b):
    spent=0
    for i in range(0,n):
        for j in range(0,m):
            if b >= keyboards[i] + drives[j] > spent:
                spent = keyboards[i] + drives[j]
                print(spent,keyboards[i],drives[j])
    spent = -1 if spent==0 else spent
    return spent
#### Counting Valleys
    def countingValleys(steps, path):
    lst=[]
    count = 0
    countx = 0
    for i in path:
        if i=='U':
            count += 1
        else:
            count -= 1
        lst.append(count)
    for i in range(0,len(lst)-1):
        if lst[i]<=0 and lst[i+1]==0:
            countx += 1
    return countx
#### Drawing book
    def pageCount(n, p):
    if n%2==0:
        if p<=n/2: #Start from left
            page_num=int(p/2)
        elif p>n/2:
            px=n-p
            page_num=int((px+1)/2)
    else:
        if p<(n+1)/2:
            if p%2==0:
                page_num=p/2
            else:
                page_num=(p-1)/2
        else:
            page_num=int((n-p)/2)
    return int(page_num)
#### Sales by Match
    
    def sockMerchant(n, ar):
        # Write your code here
        count=0
        data=dict(Counter(ar))
        for x in data.values():
            count += x//2
        return count

#### Bill Division
    
    def bonAppetit(bill, k, b):
    share = b - (sum(bill)-bill[k])/2
    if share!=0:
        share=print(int(share))
    else:
        share=print('Bon Appetit')
    return share
#### Day of the programmer
    
    def dayOfProgrammer(y):
    if 1918<y<=2700:
        if y%400==0:
            date= '12.09.{}'.format(y)
        elif y%4==0 and y%100!=0:
            date= '12.09.{}'.format(y)
        else:
            date= '13.09.{}'.format(y)
    elif 1700<=y<=1917:
        if y%4==0:
            date='12.09.{}'.format(y)
        else:
            date='13.09.{}'.format(y)
    elif y==1918:
        date='26.09.1918'
        
#### Migratory Birds
    def migratoryBirds(arr):
        arr.sort()
        data=dict(Counter(arr))
        maximum=max(data, key=data.get)
        return maximum
#### Divisible Sum Pairs

    def divisibleSumPairs(n, k, ar):
        count=0
        for i in range(0,n):
            for j in range(0,n):
                if i!=j and i<j and (ar[i]+ar[j])%k==0:
                    count += 1
        return count

#### birthday segment
    
    def birthday(s, d, m):
    count = 0
    for i in range(n-m+1):
        if sum(s[i:i+m])==d:
            count += 1
    return count
#### Breaking the Records
    
    def breakingRecords(scores):   
    mx=scores[0]
    count=0
    for i in range(0,n):
        if scores[i]>mx:
            mx=scores[i]
            count=count+1
    mxe=scores[0]
    countx=0
    for i in range(0,n):
        if scores[i]<mxe:
            mxe=scores[i]
            countx=countx+1
    return count,countx

#### Between Two Sets

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
#### Number Line Jumps

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
