# EX 6B KNAPSACK PROBLEM
## DATE: 13-05-25
## AIM:
To demonstrate a python program using dynamic programming for 0/1 knapsack problem.

## Algorithm
1. Base Case:
   - If n == 0 or W == 0, return 0 (no items or no capacity).

2. If item too heavy:
   - If wt[n-1] > W, skip the item → recurse with n-1.

3. Else - Choice:
   - Choose max of:
     - Including item: val[n-1] + knapSack(W - wt[n-1], wt, val, n-1)
     - Excluding item: knapSack(W, wt, val, n-1)

4. Return the maximum of the two choices.

## Program:
```
/*
To implement the program for 0/1 knapsack problem.
Developed by: Sowmya V
Register Number: 212222110045
*/

def knapSack(W, wt, val, n):
    if n==0 or W==0:
        return 0
    if (wt[n-1]>W):
        return knapSack(W,wt,val,n-1)
    else:
        return max(val[n-1]+knapSack(W-wt[n-1],wt,val,n-1),knapSack(W,wt,val,n-1))

x=int(input())
y=int(input())
W=int(input())
val=[]
wt=[]
for i in range(x):
    val.append(int(input()))
for y in range(y):
    wt.append(int(input()))
n = len(val)
print('The maximum value that can be put in a knapsack of capacity W is: ',knapSack(W, wt, val, n))
```

## Output:
![image](https://github.com/user-attachments/assets/34919fe9-ec01-435a-bd5f-4745250a2cee)
![image](https://github.com/user-attachments/assets/90db2c9d-b239-459b-95a2-24dfceb21b63)

## Result:
Thus the program was executed successfully for finding the maximum value that can be put in a knap sack of capacity .
