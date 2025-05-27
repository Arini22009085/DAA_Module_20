# EX 2D BACKTRACKING - GRAPH COLORING PROBLEM
## DATE:
## AIM:
To solve the Graph Coloring Problem using backtracking, assigning colors to the vertices of a graph such that no two adjacent vertices share the same color while minimizing the number of colors used.
## Algorithm
1.  Define a recursive function to assign colors to vertices one by one.
2.  At each step, check if the current color can be assigned safely (i.e., no adjacent vertex has the same color).
3.  If it is safe, assign the color and move to the next vertex by making a recursive call.
4.  If it is not safe or no color fits, backtrack: remove the assigned color and try the next available color.
5.  If all vertices are successfully colored, print the solution; else, if no valid coloring is possible, report failure.  

## Program:
```
/*
Program to implement Graph Coloring Problem using backtracking.
Developed by: ARINI A
Register Number: 212222040011
*/
```
```
class Graph():
    def __init__(self, vertices):
        self.V = vertices
        self.graph = [[0 for column in range(vertices)]for row in range(vertices)]
 
    def isSafe(self, v, colour, c):
        for i in range(self.V):
            if self.graph[v][i] == 1 and colour[i] == c:
                return False
        return True

    def graphColourUtil(self, m, colour, v):
        if v == self.V:
            return True
        for c in range(1, m + 1):
            if self.isSafe(v, colour, c) == True:
                colour[v] = c
                if self.graphColourUtil(m, colour, v + 1) == True:
                    return True
                colour[v] = 0

    def graphColouring(self, m):
        colour = [0] * self.V
        if self.graphColourUtil(m, colour, 0) == None:
            return False
        print ("Solution exist and Following are the assigned colours:")
        for c in colour:
            print (c,end=' ')
        return True
# Driver Code
```
## Output:
![image](https://github.com/user-attachments/assets/7d760797-89fd-4dfd-8c75-d6049b2d82b8)

## Result:
The Graph Coloring program executed successfully, and the colors were assigned to the vertices such that no two adjacent vertices share the same color.
