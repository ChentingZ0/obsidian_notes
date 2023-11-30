- Shape: `(m, n)`-> is always a tuple
- Ways to initialize a special matrices:
1. Identity matrix of size $n\times n$: `np.eye(n)`
2. All-zeroes matrix of size $m\times n$ : `np.zeros((m,n))`
3. All-ones matrix of size $m\times n$: `np.ones((m,n))`
4. Using lists: `B = np.array([[0,1,0],[1,0,1],[0,1,0]])`


- Common numerical computation
Matrix multiplication: `A @ B` or `np.matmul(A,B)`

Tranpose: `A.T` or `A.transpose()`

Entry-wise minumum of two matrices: 
`np.minimum(A,B)` -> returns C with $C_{ij} = min\{A_{ij}, B_{ij}\}$

Thresholding:
Suppose you want to set $A_{ij} = 0$ for all entries with $A_{ij} < 0$
`A[A<0] = 0`, 
Set $A_{ij} = k$ for all $A_{ij} < c$
`A[A<c] = k`

