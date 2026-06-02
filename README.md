# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
Step 1: Start the program.

Step 2: Read the number of unknowns n.

Step 3: Input the augmented matrix A of size n × (n+1).

Step 4: Perform forward elimination:

For each row i from 0 to n-1:
Check whether the pivot element A[i][i] is zero.
If it is zero, display "Divide by zero detected!" and stop.
For each row j = i+1 to n-1:

Compute the ratio:

ratio=
A[i][i]
A[j][i]
	​


Update the row:

A[j][k]=A[j][k]−ratio×A[i][k]

for all columns k = 0 to n.

Step 5: Perform back substitution:

Calculate the last variable:

x[n−1]=
A[n−1][n−1]
A[n−1][n]
	​

For i = n-2 down to 0:

Set:

x[i]=A[i][n]

For j = i+1 to n-1:

x[i]=x[i]−A[i][j]×x[j]

Divide by the pivot element:

x[i]=
A[i][i]
x[i]
	​


Step 6: Display the values of all unknowns x₁, x₂, ..., xₙ.

Step 7: Stop the program.


## Program:
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i]==0.0:
        sys.exit('Divide by zero detected!')
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f '%(i,x[i]),end='')

## Output:
<img width="1904" height="1036" alt="Screenshot 2026-06-02 052853" src="https://github.com/user-attachments/assets/5d8ebb4f-ad96-4572-a218-1dd9acd1d043" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

