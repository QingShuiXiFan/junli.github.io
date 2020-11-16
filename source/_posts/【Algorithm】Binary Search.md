---
title: 【Algorithm】Binary Search
tag: [Algorithm, Binary Search, EN]
thumbnail: https://www.easyicon.net/api/resizeApi.php?id=1218126&size=128
category: Algorithm
---

## Applicable Scenarios

- Search a certain number in a ** sorted ** array, under some condition.

## Code Snippets
```python
# Recursive
def bsearch(nums: list, low: int, high: int, value) -> int:
    """
    在数组nums的下标low和high之间，查找value，返回下标
    """
    if low > high:
        return -1
    middle = low + (high - low) >> 1
    if nums[middle] == value:  # 找到了
        return middle
    elif nums[middle] > value:
        return bsearch(nums, low, middle-1, value)  # high = middle-1
    else:
        return bsearch(nums, middle+1, high, value)  # low = middle+1
```

```python
# Iterative
def bsearch(nums: List[int], target: int) -> int:
    left= 0
    right=len(nums) - 1
    while left <= right: # 区间没有变成1个元素，就查找
        middle =  left + ((right-left) >> 1)  # 计算中间下标
        if nums[middle] == target:  # 找到了
            return middle
        elif nums[middle] < target:  # 中间下标比查找的值小，继续在右边查找
            left = middle + 1
        else:  # 中间下标比查找的值大，继续在左边查找
            right = middle - 1
    return -1
```