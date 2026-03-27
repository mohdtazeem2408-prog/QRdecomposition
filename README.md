# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
### Gram-Schmidt Method
```
Program to QR decomposition using the Gram-Schmidt method
Developed by: your name:Mohamed Tazeem R
RegisterNumber: 212225230177
'''
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
def QR_Decomposition(A):
    A=np.array(A,dtype=float)
    m,n=A.shape
    Q=np.zeros((m,n))
    R=np.zeros((n,n))
    for j in range(n):
        v=A[:,j]
        for i in  range(j):
            R[i,j]=np.dot(Q[:,i],A[:,j])
            v=v-R[i,j]*Q[:,i]
        R[j,j]=np.linalg.norm(v)
        Q[:,j]=v/R[j,j]
    return Q,R
A = np.array(eval(input()))
Q,R=QR_Decomposition(A)
print("The Q Matrix is\n",Q)
print("The R Matrix is\n",R)

```
## Output
```
<img width="1276" height="828" alt="image" src="https://github.com/user-attachments/assets/fde0dc47-6b29-44ed-8dd7-06330842de0f" />
<img width="1226" height="441" alt="image" src="https://github.com/user-attachments/assets/11cabbde-92a3-4b74-922a-b118f59ae71b" />

```

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
