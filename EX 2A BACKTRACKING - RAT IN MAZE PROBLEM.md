# EX 2A BACKTRACKING - RAT IN MAZE PROBLEM
## DATE: 
## AIM:
To implement the Rat in a Maze problem using backtracking and find all possible paths from the start to the destination in a given maze.
## Algorithm
1. Function Input: The function will take the maze matrix (maze), the current position (x, y), and the destination position (n-1, n-1). It will also take a path list to store the current path the rat takes.

2. Base Case: If the current position is the destination (i.e., the bottom-right corner), store the current path as a valid solution. If the current position is outside the maze, a wall (represented by 0), or already visited, backtrack by returning from the current function call.

3. Mark the Current Cell: Mark the current cell as visited to avoid revisiting it in the same path. This can be done by setting maze[x][y] to a special value (e.g., -1) or by using a visited array.

4.  Explore All Possible Directions: Try moving in all four possible directions: down, right, up, and left. For each direction, check if the move is valid (i.e., the next cell is within bounds, not blocked, and not visited). Recursively call the function to move to the next valid cell.

5. Backtrack: After exploring all possible paths from the current cell, backtrack by marking the current cell as unvisited (restore the original value of the cell). If no valid path is found, return to the previous step.

6. Return All Paths: Collect all the valid paths from the start to the destination. Each valid path is stored in a separate list. After exploring all possible paths, return the list of paths. 
## Program:
```
/*
Program to implement Rat in a Maze.
Developed by: ARINI A
Register Number: 212222040011
*/
```
```
N = 4
def printSolution( sol ):
     
    for i in sol:
        for j in i:
            print(str(j) + " ", end ="")
        print("")
def isSafe( maze, x, y ):
    if x >= 0 and x < N and y >= 0 and y < N and maze[x][y] == 1:
        return True    
    return False
def solveMaze( maze ):
     
    # Creating a 4 * 4 2-D list
    sol = [ [ 0 for j in range(4) ] for i in range(4) ]
     
    if solveMazeUtil(maze, 0, 0, sol) == False:
        print("Solution doesn't exist");
        return False  
    printSolution(sol)
    return True
def solveMazeUtil(maze, x, y, sol):    
#Write your code here
      if x == N - 1 and y == N - 1:
        sol[x][y] = 1
        return True
      if isSafe(maze, x, y) == True:
        sol[x][y] = 1
        if solveMazeUtil(maze, x + 1, y, sol) == True:
            return True
        if solveMazeUtil(maze, x, y + 1, sol) == True:
            return True
        sol[x][y] = 0
        return False
# Driver program to test above function
if __name__ == "__main__":
    # Initialising the maze
    maze = [ [1, 0, 0, 0],
             [1, 1, 0, 1],
             [0, 1, 0, 0],
             [1, 1, 1, 1] ]
              
    solveMaze(maze)
```
## Output:
![image](https://github.com/user-attachments/assets/4f7fa150-216e-4001-9e69-f5a6be407377)

## Result:
The Rat in a Maze program executed successfully, and a valid path from the start to the destination was found and display.
