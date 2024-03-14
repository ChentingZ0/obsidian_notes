### House robber 1
https://leetcode.cn/problems/house-robber/
```python
```python
class Solution:
    def rob(self, nums: List[int]) -> int:
        if not nums or nums == [0]:
            return 0
        else:
            n = len(nums)
            if n == 1:
                return nums[0]
            else:
                dp = [0] * n
                dp[0] = nums[0]
                dp[1] = max(nums[0], nums[1])
                for i in range(2, n):
                    dp[i] = max(dp[i-1], dp[i-2] + nums[i])
                return dp[-1]
```
减小空间复杂度 ->
```python
```python
class Solution:
    def rob(self, nums: List[int]) -> int:
        # 减小空间复杂度
        # No need to store all the dp values, only two pointers are needed, update iteratively
        cur, pre = 0, 0
        for num in nums:
            cur, pre = max(pre + num, cur), cur
        return cur
```

### House robber 2
把环分成两个单排 
ans = max(nums[1:], nums[: n-1])