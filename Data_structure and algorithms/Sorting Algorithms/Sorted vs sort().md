Python built-in function

`sort()` function in Python will change the original order of the list

The `sorted()` function in Python uses an adaptive and stable sorting algorithm called Timsort.

Timsort is a hybrid sorting algorithm derived from merge sort and insertion sort. It was designed by Tim Peters and is the standard sorting algorithm in Python since version 2.3. Timsort performs well on many kinds of real-world data and is particularly efficient on partially ordered data, which is a common use case.

Timsort has an average and worst-case time complexity of O(nlogn) and a best-case time complexity of O(n) when the input is already partially ordered or small enough. It's stable, which means that the relative order of elements with equal keys remains preserved.

```python
nums = [1,5,7,2,4]
nums.sort()
new_list = sorted(nums)
```
