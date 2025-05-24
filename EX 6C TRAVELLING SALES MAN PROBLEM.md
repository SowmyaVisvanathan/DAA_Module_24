# EX 6C TRAVELLING SALES MAN PROBLEM
## DATE: 17-05-25
## AIM: To Solve Travelling Sales man Problem for the following graph.
![image](https://github.com/user-attachments/assets/653921a4-3d7b-4691-9b41-735e80f7af0b)

## Algorithm:   
1. Input:
   - A graph[V][V] representing travel costs, and starting point s.

2. List All Cities:
   - Exclude the starting city s from the list of vertices to visit.

3. Generate All Permutations:
   - Try all possible orders of visiting the remaining cities.

4. Calculate Path Cost for each permutation:
   - Start from city s.
   - Sum up distances along the path.
   - Add cost to return back to city s.

5. Track Minimum Path:
Keep the minimum path cost among all permutations.

6. Return the minimum cost path.


## Program:
```
/*
To implement the program for TSP.
Developed by: Sowmya V
Register Number: 212222110045
*/

from sys import maxsize
from itertools import permutations
V = 4
def travellingSalesmanProblem(graph, s):
    vertex =[]
    for i in range(V):
        if i !=s:
            vertex.append(i)
    min_path = maxsize
    next_permutation = permutations(vertex)
    for i in next_permutation:
        current_pathweight = 0
        k = s
        for j in i:
            current_pathweight += graph[k][j]
            k = j
        current_pathweight += graph[k][s]
        min_path = min(min_path, current_pathweight)
        
    return min_path
if __name__ == "__main__":
 
    graph = [[0, 10, 15, 20], [10, 0, 35, 25],
            [15, 35, 0, 30], [20, 25, 30, 0]]
    s = 0
    print(travellingSalesmanProblem(graph, s))
    
```
## Output:
![image](https://github.com/user-attachments/assets/cfd0e135-6b71-42ea-ac27-a4386e595710)

## Result:
Thus the program was executed successfully for finding the minimum cost to vist all cities.
