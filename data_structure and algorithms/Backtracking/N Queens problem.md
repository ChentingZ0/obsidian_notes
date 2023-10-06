[leetcode](https://leetcode.com/problems/n-queens/)

Draw the decision tree:
![[Pasted image 20231006215155.png]]

**Programming mindset**:
Choice: 
Which column do we place our queen in at every row. Make a choice at every row.

Constraints:
not place in the same row, column, diagonal

Goal:
n columns of queens place, finished the recursion and we can backtrack to the most recent spot and keep 

[Well explained video](https://www.youtube.com/watch?v=wGbuCyNpxIg&ab_channel=BackToBackSWE)
Main procedure(key): Goal(base case), Choice(make a decision, then go to deeper recursion), Undo Choice
then trust :D
```java
private static void solveNQueens(int n, int row, List<Integer> colplacements, List<List<Integer>> result){
	if(row == n){
		result.add(new ArrayList<>(colPlacements));
	}
	else {
		for(int col = 0; col < n; col++){
			colPlacements.add(col)
			if(isValid(colPlacements)){
				solveNQueens(n, row+1, colPlacements, result);
			}
	colPlacements.remove(colPlacements.size()-1)
		}
	}
}
```

For isValid helper function: 略
```java
private static boolean isValid(){
	......
}
```

Here's the Python code 
```python
class Solution:
def solveNQueens(self, n: int) -> List[List[str]]:
# not in the same row, column, diagnol
	col = set()
	posDiag = set() # r+c
	negDiag = set() # r-c
	result = []
	board = [["."] * n for i in range(n)]
	def backtrack(r):
		if r == n:
			copy = ["".join(row) for row in board]
			result.append(copy)
		return 
		## Goal, base case, when to stop the recursion!
	
	for c in range(n):
		if c in col or (r+c) in posDiag or (r-c) in negDiag:
		continue
	
		col.add(c) 
		posDiag.add(r + c)	
		negDiag.add(r - c)
		board[r][c] = "Q"
		## Make the choice	
		backtrack(r+1) 
		## Go into recursion, check the next
		
		col.remove(c) ## Undo the choice
		posDiag.remove(r + c)	
		negDiag.remove(r - c)
		board[r][c] = "."
backtrack(0)
return result
```