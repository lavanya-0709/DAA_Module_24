# EX 6B KNAPSACK PROBLEM
## DATE: 29/04/2025
## AIM:
To demonstrate a python program using dynamic programming for 0/1 knapsack problem.



## Algorithm
1. Create a 2D DP table dp[n+1][W+1] to store the max value for each item and weight capacity.

2. Initialize the first row and column of the table with 0 (no items or no capacity).
   
3. If the item's weight ≤ current capacity:

     dp[i][w] = max(value with item, value without item)

5. Else:

    dp[i][w] = value without item

6. Return the value at dp[n][W] — the max value you can carry. 

## Program:
```
/*
To implement the program for 0/1 knapsack problem.


Developed by: LAVANYA S
Register Number: 212223230112
*/
def knapSack(W, wt, val, n):
	if n == 0 or W == 0 :
		return 0
	if (wt[n-1] > W):
		return knapSack(W, wt, val, n-1)
	else:
		return max(val[n-1] + knapSack(W-wt[n-1], wt, val, n-1), knapSack(W, wt, val, n-1))
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

![image](https://github.com/user-attachments/assets/9c422f87-c6a0-4fad-a815-7d6a64666670)


## Result:
Thus the program was executed successfully for finding the maximum value that can be put in a knap sack of capacity .
