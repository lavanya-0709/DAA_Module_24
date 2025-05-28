# EX 6A CHERRY PICK UP PROBLEM
## DATE: 26/04/2025
## AIM:
To Create a python program for the following problem statement.
You are given an n x n grid representing a field of cherries, each cell is one of three possible integers.
0	means the cell is empty, so you can pass through,
1	means the cell contains a cherry that you can pick up and pass through, or
-1 means the cell contains a thorn that blocks your way.
Return the maximum number of cherries you can collect by following the rules below:
Starting at the position (0, 0) and reaching (n - 1, n - 1) by moving right or down through valid path cells (cells with value 0 or 1).
After reaching (n - 1, n - 1), returning to (0, 0) by moving left or up through valid path cells.
When passing through a path cell containing a cherry, you pick it up, and the cell becomes an empty cell 0. If there is no valid path between (0, 0) and (n - 1, n - 1), then no cherries can be collected.



## Algorithm
1.Start at (0, 0), move to (n-1, n-1) (only right or down)

2.Then return back to (0, 0) (only left or up)

3.Can pass through cells with 0 or 1

4.Can pick cherries (1) only once (cell becomes 0 after pick)

5.Avoid thorns (-1) 
  

## Program:
```
/*
To implement the program for Cherry pickup problem.


Developed by: LAVANYA S
Register Number: 212223230112
*/
class Solution:
    def cherryPickup(self, grid):
        n = len(grid)
        dp = [[-1] * (n + 1) for _ in range(n + 1)]
        dp[1][1] = grid[0][0]
        for m in range(1, (n << 1) - 1):
            for i in range(min(m, n - 1), max(-1, m - n), -1):
                for p in range(i, max(-1, m - n), -1):
                    j, q = m - i, m - p
                    if grid[i][j] == -1 or grid[p][q] == -1:
                        dp[i + 1][p + 1] = -1
                    else:
                        dp[i + 1][p + 1] = max(dp[i + 1][p + 1], dp[i][p + 1], dp[i + 1][p], dp[i][p])
                        if dp[i + 1][p + 1] != -1: dp[i + 1][p + 1] += grid[i][j] + (grid[p][q] if i != p else 0)
        return max(0, dp[-1][-1])
        n,m=len(grid),len(grid[0])
        dp = [[[-1 for i in range(m)] for j1 in range(n)] for j2 in range(n)]

        return f(0,0,m-1,dp)
obj=Solution()
grid=[[0,1,-1],[1,0,-1],[1,1,1]]        
print(obj.cherryPickup(grid))
```

## Output:

![image](https://github.com/user-attachments/assets/47ab9b03-0590-4e26-ae19-cc7ddfaf617b)


## Result:
Thus the above program was executed successfully for finding the maximum number of cherries from grid.
