[sum of three](https://leetcode.cn/problems/3sum/?envType=study-plan-v2&envId=huawei-2023-fall-sprint)
![[Pasted image 20240311194803.png]]


**解答：**
![[Pasted image 20240311194904.png]]

```python
class Solution:
    def threeSum(self, nums: List[int]) -> List[List[int]]:
        # brute-force O(n^3)
        # optimization through two pointers -> k(fixed), i, j(end)
        nums.sort()
        res = []
        k = 0
        for k in range(len(nums)-2):
            if nums[k] > 0:
                break
            if k > 0 and nums[k] == nums[k-1]:
                continue
            i, j = k + 1, len(nums) - 1
            while i < j:
                s = nums[k] + nums[i] + nums[j]
                if s < 0:
                    i += 1
                    while i < j and nums[i] == nums[i-1]:
                        i += 1
                elif s > 0:
                    j -= 1
                    while i < j and nums[j] == nums[j+1]:
                        j -= 1
                else:
                    res.append([nums[k], nums[i], nums[j]])
                    i += 1
                    j -= 1
                    while i < j and nums[i] == nums[i-1]:
                        i += 1
                    while i < j and nums[j] == nums[j+1]:
                        j -= 1
        return res
```
