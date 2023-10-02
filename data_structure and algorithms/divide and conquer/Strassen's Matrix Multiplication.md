$[a11,a12;a21,a22] \times [b11,b12;b21,b22] = [c11,c12;c21,c22]$

**Intuition**:
```c++
for(i=0; i<n; i++){
	for(j=0; j<n; j++){
		C[i,j] = 0
		for(k=0; k<n; k++){
			C[i,j] += A[i,k]*B[k,j];
		}
	}
}
```
Time complexity is $O(n^3)$

What if the dimension n goes large??!
Break into small problems -> For large matrix n, partition it into four $n/2\times n/2$ matrices. The base case is $1\times 1$ matrix. 
![[Pasted image 20231002230850.png]]
![[Pasted image 20231002231413.png]]
The algorithm goes: (pseudo code)
```python
def Matrix_Multiply_Recursive(A,B):
	n = A.rows
	Let C be n*n matrix
	if n==1:
		c11 = a11 * b11
	else partition A,B,C as (4.9):
		C11 = A11 * B11 + A12 * B21
		C12 = A11 * B12 + A12 * B22
		C21 = A21 * B11 + A22 * B21
		C22 = A21 * B12 + A22 * B22
	return C
```

When n == 1, $T(1) = O(1)$
When n > 1, $T(n)  = 8T(n/2) + O(n^2)$

So the overall complexity is $O(n^{log_{2}8}) = O(3)$
Multiplying partitioned matrices takes 8 times, each is n/2 dimension -> 8T(n/2)  (recursive)
Adding partitioned matrices takes $O(n^2)$

#### Strassen's method
![[Pasted image 20231002234025.png]]
reduce the times of multiplication, math game?! :D
$T(n) = 7T(n/2) + O(n^2)$ if n > 1

effective :D a bit
