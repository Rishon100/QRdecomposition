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
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: V RISHON ANAND
RegisterNumber: 212224240135
'''
import numpy as np
def QR_Decomposition(A):
    n,m = A.shape # get the shape of A
    Q = np.empty((n,n)) # initialize matrix Q
    u = np.empty((n,n)) # initialize matrix u
    u[:,0] = A[:,0]
    Q[:,0] = u[:,0] / np.linalg.norm(u[:,0])
    for i in range(1,n):
        u[:,i] = A[:,i]
        for j in range(i):
            u[:,i] -= (A[:,i]@Q[:,j]*Q[:,j]) #get each u vector
        Q[:,i] = u[:,i]/np.linalg.norm(u[:,i]) # compute each e vector 
    R = np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            R[i,j]=A[:,j]@Q[:,i]
    print("The Q Matrix is\n",Q)
    print("The R Matrix is\n",R)
    
a = np.array(eval(input()))
QR_Decomposition(a)






```

## Output

<img width="1243" height="482" alt="image" src="https://github.com/user-attachments/assets/4230b796-f011-4f9d-b94d-2d78bb298e68" />
<img width="1240" height="643" alt="image" src="https://github.com/user-attachments/assets/6941c240-3125-48e2-886c-652516076843" />
<img width="1231" height="612" alt="image" src="https://github.com/user-attachments/assets/777d0127-22ea-4990-932b-e5d7a554d830" />


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
