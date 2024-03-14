![[Pasted image 20240229194602.png]]
```python
class Solution:
    def longestPalindrome(self, s: str) -> str:
        n = len(s)
        if n < 2:
            return s
        # dp[i][j] 表示 s[i...j]是否是回文串, boolean
        # Initialization -> n * n
        
        begin = 0
        max_len = 1
        dp = [[False] * n for _ in range(n)]
        for i in range(n):
            dp[i][i] = True
            
        # Recursion
        # Take care of the loop order(short substring -> long substring)
        for L in range(2, n + 1):
            for i in range(n):
                j = i + L - 1
                if j >= n:
                    break
                if s[i] != s[j]:
                    dp[i][j] == False
                else:
                    if j == i+1 or j == i+2:
                        dp[i][j] = True
                    else:
                        dp[i][j] = dp[i+1][j-1]
                if dp[i][j] == True and j - i + 1 > max_len:
                    max_len = j - i + 1
                    begin = i
        return s[begin: begin + max_len]
```


![[Pasted image 20240229200156.png]]
```python
class Solution:
    def expandAroundCenter(self, s, left, right):
        while left >= 0 and right < len(s) and s[left] == s[right]:
            left -= 1
            right += 1
        return left + 1, right - 1
        
    def longestPalindrome(self, s: str) -> str:
        start, end = 0, 0
        for i in range(len(s)):
            left1, right1 = self.expandAroundCenter(s, i, i)
            left2, right2 = self.expandAroundCenter(s, i, i+1)
            if right1 - left1 > end - start:
                start, end = left1, right1
            if right2 - left2 > end - start:
                start, end = left2, right2
        return s[start: end + 1]
```
