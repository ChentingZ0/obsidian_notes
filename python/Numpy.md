
- Ways to initialize a special matrices:
 Shape: `(m, n)`-> is always a tuple
1. Identity matrix of size $n\times n$: ==`np.eye(n)`==
2. All-zeroes matrix of size $m\times n$ : ==`np.zeros((m,n))`==
3. ==`np.zeros_like()`==
4. All-ones matrix of size $m\times n$: ==`np.ones((m,n))`==
5. Using lists: ==`B = np.array([[0,1,0],[1,0,1],[0,1,0]])`==


Matrix multiplication: ==`A @ B`== or `np.matmul(A,B)`

Tranpose: ==`A.T`== or==`A.transpose()`==


Entry-wise minumum of two matrices: 
==`np.minimum(A,B)`== -> returns C with $C_{ij} = min\{A_{ij}, B_{ij}\}$

Thresholding:
Suppose you want to set $A_{ij} = 0$ for all entries with $A_{ij} < 0$
==`A[A<0] = 0`==, 
Set $A_{ij} = k$ for all $A_{ij} < c$
==`A[A<c] = k`==

==`np.linalg`==:

==`np.vectorize()`==:

==`has_no_zero = np.all(array != 0)`:==

`array != 0`: This part creates a boolean array of the same shape as `array`. Each element of this new array is `True` if the corresponding element in `array` is not equal to zero, and `False` if it is equal to zero.

For example, if `array` is `[1, 2, 0, 4]`, then `array != 0` evaluates to `[True, True, False, True]`.

The numpy `all()` function returns `True` if all elements in an array (or along a given axis) evaluate to `True`.

If there's even one `False` in the input, `np.all()` returns `False`.

==`np.any()`==

==`np.linalg`==
np.linalg.matrix_power(A, n)

==`np.convolve`==

==`np.meshgrid`==
Create a rectangular grid out of two given one-dimensional arrays. Useful for converting coordinate vectors.

- `np.meshgrid` will create two 2D matrices corresponding to all pairs of `(X, Y)` in the two arrays.
- The first matrix (`XX`) will be a replication of the x-axis vector for each row and will contain the x-coordinates.
- The second matrix (`YY`) will be a replication of the y-axis vector for each column and will contain the y-coordinates.
- Example:
```python
import numpy as np

x = np.array([0, 1, 2])
y = np.array([0, 1, 2, 3])
XX, YY = np.meshgrid(x, y)

# output:
XX = [[0 1 2]
      [0 1 2]
      [0 1 2]
      [0 1 2]]

YY = [[0 0 0]
      [1 1 1]
      [2 2 2]
      [3 3 3]]

```