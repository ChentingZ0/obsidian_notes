Data structure: dictionary(python)

例题1：
[Isomorphic Strings](https://www.youtube.com/watch?v=7yF-U1hLEqQ&ab_channel=NeetCode)(同构字符串)
用两个哈希表记录映射
```python
def isIsomorphic(self, s: str, t: str) -> bool:
	# Use HashMap to represent this mapping relationship
	mapST = {}
	mapTS = {}
	# Iterate through two strings simutaneously
	for char1, char2 in zip(s, t):
		if (char1 in mapST and mapST[char1] != char2) or (char2 in mapTS and mapTS[char2] != char1):
			return False
		else:
			mapST[char1] = char2
			mapST[char2] = char1
	return True
```

例题2：
[Word Pattern](https://leetcode.cn/problems/word-pattern/solutions/)(单词规律):
由字符到字符的映射 -> 字符到字符串的映射

```python
def wordPattern(self, pattern: str, s: str) -> bool:
	words = s.split(" ")
	if len(pattern) != len(words):
		return False
	map_ctw = {}
	map_wtc = {}
	for char, word in zip(pattern, words):
		if (char in map_ctw and map_ctw[char] != word) or (word in map_wtc and map_wtc[word] != char):
			return False
		map_ctw[char] = word
		map_wtc[word] = char
	return True
```