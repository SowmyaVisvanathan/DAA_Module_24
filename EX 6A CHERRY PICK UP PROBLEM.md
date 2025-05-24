# EX 6A CHERRY PICK UP PROBLEM
## DATE: 13-05-25
## AIM:
To Create a python program for the following problem statement.
- You are given an n x n grid representing a field of cherries, each cell is one of three possible integers.
- 0	means the cell is empty, so you can pass through
- 1	means the cell contains a cherry that you can pick up and pass through
- -1 means the cell contains a thorn that blocks your way.
- Return the maximum number of cherries you can collect by following the rules below:
- Starting at the position (0, 0) and reaching (n - 1, n - 1) by moving right or down through valid path cells (cells with value 0 or 1).
- After reaching (n - 1, n - 1), returning to (0, 0) by moving left or up through valid path cells.
- When passing through a path cell containing a cherry, you pick it up, and the cell becomes an empty cell 0.
- If there is no valid path between (0, 0) and (n - 1, n - 1), then no cherries can be collected.

## Algorithm
1. Let n = len(grid).
2. Create a 2D array dp[n][n] initialized to 0.
3. Traverse the grid from bottom-right to top-left:
   - For each cell (i, j):
     - If at bottom-right: dp[i][j] = grid[i][j]
     - If in last row: dp[i][j] = grid[i][j] + dp[i][j+1]
     - If in last column: dp[i][j] = grid[i][j] + dp[i+1][j]
     - Else: dp[i][j] = grid[i][j] + max(dp[i+1][j], dp[i][j+1])
4. Return max(0, dp[0][0]) + 1 as the result.  

## Program:
```
/*
To implement the program for Cherry pickup problem.
Developed by: Sowmya V
Register Number: 212222110045
*/

class Solution:
    def cherryPickup(self, grid):
        n = len(grid)
        dp = [[0]*n for _ in range(n)]
        for i in range(n-1,-1,-1):
            for j in range(n-1,-1,-1):
                if i == n-1 and j==n-1:
                    dp[i][j] = grid[i][j]
                elif i ==n-1:
                    dp[i][j] = grid[i][j]+dp[i][j+1]
                elif j == n-1:
                    dp[i][j] = grid[i][j] + dp[i+1][j]
                else:
                    dp[i][j] = grid[i][j] + max(dp[i][j+1],dp[i+1][j])
                    
        return max(0,dp[0][0])+1            
        
        
obj=Solution()
grid=[[0,1,-1],[1,0,-1],[1,1,1]]        
print(obj.cherryPickup(grid))
```
## Output:
![image](https://github.com/user-attachments/assets/7cd49302-ff91-48f8-bf06-6ce8d1e7535e)

## Result:
Thus the above program was executed successfully for finding the maximum number of cherries from grid.
