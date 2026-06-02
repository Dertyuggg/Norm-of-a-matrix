# Norm of a matrix
## Aim
To write a program to find the 1-norm, 2-norm and infinity norm of the matrix and display the result in two decimal places.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
	1. Get the input matrix using np.array()   
    2. Find the 2-norm of the matrix using np.linalg.norm()
	3. Print the norm of the matrix in two decimal places.
## Program:
```Python
# Register No: 212225040078
# Developed By: Dhyaneshwar S
# 1-Norm of a Matrix
import numpy as np

A = np.array(eval(input()), dtype=float)

print(f"{np.linalg.norm(A, 2):.2f}")

# 2-Norm of a Matrix
A = eval(input())

m = len(A)
n = len(A[0])

B = [[0]*n for _ in range(n)]

for i in range(n):
    for j in range(n):
        s = 0
        for k in range(m):
            s += A[k][i] * A[k][j]
        B[i][j] = s

x = [1.0] * n

for _ in range(50):
    y = [0.0] * n
    for i in range(n):
        for j in range(n):
            y[i] += B[i][j] * x[j]

    norm = sum(v * v for v in y) ** 0.5
    x = [v / norm for v in y]

lam = 0.0
for i in range(n):
    t = 0.0
    for j in range(n):
        t += B[i][j] * x[j]
    lam += x[i] * t

print(f"{lam ** 0.5:.2f}")

# Infinity Norm of a Matrix
A = eval(input())

inf_norm = 0

for row in A:
    row_sum = sum(abs(x) for x in row)
    if row_sum > inf_norm:
        inf_norm = row_sum

print(f"{inf_norm:.2f}")
```
## Output:
### 1-Norm of a Matrix
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/1aa15a21-edf4-4051-910d-c016c0fbe7f5" />


### 2-Norm of a Matrix
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/2ce12abf-e844-4d40-9e3f-0c8fc4e854d1" />



### Infinity Norm of a Matrix
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/3aa241fb-486b-4857-b42d-4bf44ded2d03" />


## Result
Thus the program for 1-norm, 2-norm and Infinity norm of a matrix are written and verified.
