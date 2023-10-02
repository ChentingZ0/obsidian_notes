分治测略 Recursive
```python
DAC(P)
{
 if small(P):
	 S(P)
 else:
	 divide P into P1,P2,P3...Pk
	 And DAC(P1), DAC(P2) ... 
	 combine(DAC(P1),DAC(P2), ...)
}
```

Example:
1. Binary Search
2. Finding Maximum and Minimum
3. [[Merge Sort]]
4. [[Quick Sort]]
5. [[Strassen's Matrix Multiplication]]