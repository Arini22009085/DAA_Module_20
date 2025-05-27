# EX 2C BACKTRACKING- SUBSET SUM PROBLEM
## DATE:
## AIM:
To demonstrate that the sum of the subset of a given set is equal to the given sum.


## Algorithm
1. Input the array a: Read the number of elements and then read the elements into list a.
2. Input the target sum that needs to be achieved by any subset of a.
3. Define a recursive function SubsetSum() to check whether the target sum can be achieved.
4. At each step, either include the current element in the sum or exclude it, and move to the next element.
5. Print "True, subset found" if a subset exists that matches the target; otherwise, print "False, subset not found".
## Program:
```
/*
Program to implement Subset sum problem.
Developed by: ARINI A
Register Number:  212222040011
*/
```
```
def SubsetSum(a, i, current_sum, target, n):
    if current_sum == target:
        return True
    if i == n or current_sum > target:
        return False

    if SubsetSum(a, i + 1, current_sum + a[i], target, n):
        return True

    return SubsetSum(a, i + 1, current_sum, target, n)

a = []
size = int(input())
for i in range(size):
    x = int(input())
    print(x)
    a.append(x)

target = int(input())
n = len(a)
if SubsetSum(a, 0, 0, target, n):
    print("True,subset found")
else:
    print("False,subset not found")
```
## Output:
![Screenshot 2025-04-26 110636](https://github.com/user-attachments/assets/17b6bead-950a-4353-be50-4e6b2f522d73)
## Result:
The Subset Sum program executed successfully, and the result was determined based on whether a subset matching the target sum was found or not.
