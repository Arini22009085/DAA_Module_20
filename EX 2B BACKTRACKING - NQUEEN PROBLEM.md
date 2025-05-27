# EX 2B BACKTRACKING - NQUEEN PROBLEM
## DATE:
## AIM:
To solve the N-Queen problem using backtracking, which places N queens on an N*N chessboard such that no two queens threaten each other.


## Algorithm
1. Read the value of N and create an N x N chessboard initialized with 0s.
2. Define a function isSafe() to check if a queen can be placed at a given position by ensuring no other queens threaten it horizontally, and diagonally (upper-left and lower-left).
3. Use a recursive function solveNQUtil() that tries to place queens column by column.
4. If a safe position is found, place the queen and recursively try to place the rest; if it fails, backtrack and remove the queen.
5. Print the board if a solution is found; otherwise, print "Solution does not exist".   
## Program:
```
/*
Program to implement N-Queen problem using backtracking.
Developed by: ARINI A
Register Number:  212222040011
*/
```
```
global N
N = int(input())

def printSolution(board):
    for i in range(N):
        for j in range(N):
            print(board[i][j], end=" ")
        print()

def isSafe(board, row, col):
    for i in range(col):
        if board[row][i] == 1:
            return False

    for i, j in zip(range(row, -1, -1), range(col, -1, -1)):
        if board[i][j] == 1:
            return False

    for i, j in zip(range(row, N, 1), range(col, -1, -1)):
        if board[i][j] == 1:
            return False

    return True

def solveNQUtil(board, col):
    if col >= N:
        return True

    for i in range(N):
        if isSafe(board, i, col):
            board[i][col] = 1
            if solveNQUtil(board, col + 1):
                return True
            board[i][col] = 0

    return False

def solveNQ():
    board = [[0 for _ in range(N)] for _ in range(N)]
    
    if not solveNQUtil(board, 0):
        print("Solution does not exist")
        return False

    printSolution(board)
    return True

solveNQ()
```
## Output:
![Screenshot 2025-04-26 110319](https://github.com/user-attachments/assets/e99280b5-30fe-4c6d-a480-59f5d68983b6)
## Result:
The N-Queens program executed successfully, and a valid board configuration was generated.
