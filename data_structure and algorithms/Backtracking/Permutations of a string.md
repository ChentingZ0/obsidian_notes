### Permutations
[leetcode](https://leetcode.com/problems/permutations/)

Decision tree:
![[Pasted image 20231006225528.png]]
Build from an empty list
Backtrack(base case, add, backtrack, remove)
```java
class Solution { 
	public List<List<Integer>> permute(int[] nums){ List<List<Integer>> resultList = new ArrayList<>(); 
	backtrack(resultList, new ArrayList<>(), nums); 
	return resultList; } 


	private void backtrack(List<List<Integer>> resultList, ArrayList<Integer> tempList, int[] nums){ 
	// base case
	if(tempList.size() == nums.length){
	resultList.add(new ArrayList<>(tempList));
	return; }  

	for(int number : nums){ 
	// skip if add the same element
		if (tempList.contains(number)) 
			continue; 
		tempList.add(number); 
		backtrack(resultList, tempList, nums);
		tempList.remove(tempList.size()-1); 
		} 
	} 
}
```