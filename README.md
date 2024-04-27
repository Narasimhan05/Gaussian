# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import the numpy module to use the built-in functions for calculation
2.Prepare the lists from each linear equations and assign in np.array()
3.Use Gaussian elimination without partial pivoting to solve a matrix. .
4.End the program

## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: NARASIMHAN S
RegisterNumber: 212223230133
'''
import numpy as np
import sys

n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][j]==0.0:
        sys.exit("Divide by zero detected")
        
    for j in range(i+1,n):
        ratio = a[j][i]/a[i][i]
        
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio * a[i][k]
            
x[n-1]=a[n-1][n]/a[n-1][n-1]

for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    
    x[i]=x[i]/a[i][i]
    
for i in range(n):
    print("X%d = %0.2f" %(i,x[i]), end=' ')
```

## Output:
![Screenshot 2024-04-27 084908](https://github.com/Narasimhan05/Gaussian/assets/132819871/a3d61958-8287-4437-904b-e5f48660cd8e)

![Screenshot 2024-04-27 084928](https://github.com/Narasimhan05/Gaussian/assets/132819871/7350054b-72cc-409f-a60c-5367b1897ad6)

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

