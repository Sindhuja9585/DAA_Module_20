# EX 2A BACKTRACKING - RAT IN MAZE PROBLEM
## DATE:07/05/2025
## AIM:
To implement the Rat in a Maze problem using backtracking and find all possible paths from the start to the destination in a given maze.


## Algorithm
1. Start from the top-left cell of the maze.

2. Move forward only if the current cell is within bounds and not blocked (i.e., value is 1).

3. Mark the current cell in the solution path.

4. Recursively try to move right or down to reach the destination.

5. If no move leads to the destination, backtrack and unmark the cell.   

## Program:
```
/*
Program to implement Rat in a Maze.
Developed by: SINDHUJA P
Register Number: 212222220047
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
    if(x==N-1 and y==N-1):
        sol[x][y]=1
        return True
    elif(isSafe(maze,x,y)==True):
        sol[x][y]=1
        if(solveMazeUtil(maze,x+1,y,sol)==True):
            return True
        if(solveMazeUtil(maze,x,y+1,sol)==True):
            return True
        sol[x][y]=0
        return False
    return False


if __name__ == "__main__":
    # Initialising the maze
    maze = [ [1, 0, 0, 0],
             [1, 1, 0, 1],
             [0, 1, 0, 0],
             [1, 1, 1, 1] ]
              
    solveMaze(maze)
```

## Output:
![image](https://github.com/user-attachments/assets/02e4bb3e-5425-440f-8b9e-dc59311ee6e7)

## Result:
The Rat in a Maze program executed successfully, and a valid path from the start to the destination was found and display.
