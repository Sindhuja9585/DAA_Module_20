# EX 2D BACKTRACKING - GRAPH COLORING PROBLEM
## DATE: 07/05/2025
## AIM:
To solve the Graph Coloring Problem using backtracking, assigning colors to the vertices of a graph such that no two adjacent vertices share the same color while minimizing the number of colors used.

## Algorithm
1. Try to assign colors (1 to m) to each vertex of the graph.

2. For each vertex, check if the chosen color is safe (no adjacent vertex has the same color).

3. If safe, assign the color and move to the next vertex recursively.

4. If coloring fails for a vertex, backtrack and try a different color.

5. If all vertices are colored successfully, print the color assignments. 
  

## Program:
```
/*
Program to implement Graph Coloring Problem using backtracking.
Developed by: SINDHUJA P
Register Number: 212222220047
*/
```
```
class Graph:
    def __init__(self,vertices):
        self.v=vertices
        self.graph=[[0 for column in range(vertices)] for row in range(vertices)]
    def isSafe(self,v,colour,c):
        for i in range(self.v):
            if self.graph[v][i]==1 and colour[i]==c:
                return False
        return True
    def graphColouringUtil(self,m,colour,v):
        if v==self.v:
            return True
        for c in range(1,m+1):
            if self.isSafe(v,colour,c):
                colour[v]=c
                if self.graphColouringUtil(m,colour,v+1):
                    return True
                colour[v]=0
        return False
    def graphColouring(self,m):
        colour=[0]*self.v
        if not self.graphColouringUtil(m,colour,0):
            return False
        return colour
g=Graph(4)
g.graph=[[0,1,1,1],[1,0,1,0],[1,1,0,1],[1,0,1,0]]
m=3
result=g.graphColouring(m)
if result:
    print("Solution exist and Following are the assigned colours:")
    for c in result:
        print(c,end=" ")
else:
    print("f")
```

## Output:
![image](https://github.com/user-attachments/assets/f748786d-36d6-45aa-8dbb-b0049bcb5966)

## Result:
The Graph Coloring program executed successfully, and the colors were assigned to the vertices such that no two adjacent vertices share the same color.
