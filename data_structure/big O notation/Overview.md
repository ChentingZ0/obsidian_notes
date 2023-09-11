```
a=5
b=6
c=10
for i in range(n):
   for j in range(n):
      x = i * i
      y = j * j
      z = i * j
for k in range(n):
   w = a*k + 45
   v = b*b
d = 33
```
In this case, $T(n) = 3+3n^{2}+2n+1$, $n^{2}$ term be the dominant, so it's $O(n^{2})$
[Textbook](https://runestone.academy/ns/books/published/pythonds/AlgorithmAnalysis/BigONotation.html)

The examples of different big O notation are as follows:
[[O(1)]] > [[O(log(n))]] > [[O(n)]] > [[O(nlog(n))]]> [[O(n^2)]]> O(n^3) > [[O(2^n)]]> O(n!)
