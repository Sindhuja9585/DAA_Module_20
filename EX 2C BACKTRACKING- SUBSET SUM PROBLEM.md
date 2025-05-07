# EX 2C BACKTRACKING- SUBSET SUM PROBLEM
## DATE:07/05/2025
## AIM:
To demonstrate that the sum of the subset of a given set is equal to the given sum.


## Algorithm
1. Start from the first element and explore all subsets by including or excluding current element.

2. Maintain a running sum while recursively traversing the array.

3. If end of array is reached, check if current sum equals the target.

4. If any recursive path leads to the target sum, return True.

5. If no subset adds up to the target, return False. 

## Program:
```
/*
Program to implement Subset sum problem.
Developed by: SINDHUJA P
Register Number:  212222220047
*/
```
```
def SubsetSum(a,i,sum,target,n):

    if(i==n):
        return sum==target
    if SubsetSum(a,i+1,sum+a[i],target,n):
        return True
    if SubsetSum(a,i+1,sum,target,n):
        return True
        
    return False

a=[]
size=int(input())
for i in range(size):
    x=int(input())
    a.append(x)

target=int(input())
n=len(a)
if(SubsetSum(a,0,0,target,n)==True):
    for i in range(size):
        print(a[i])
    print("True,subset found")
else:
    for i in range(size):
        print(a[i])
    print("False,subset not found")

```

## Output:
![image](https://github.com/user-attachments/assets/90c6a834-77b4-4e70-ac3f-e4cf84506626)

## Result:
The Subset Sum program executed successfully, and the result was determined based on whether a subset matching the target sum was found or not.
