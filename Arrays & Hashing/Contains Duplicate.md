---
tags:
  - ArraysAndHashing
date: 2026-09-28
---
## Problem
___
Given an integer array `nums`, return `true` if any value appears **more than once** in the array, otherwise return `false`.

**Example 1:**

```java
Input: nums = [1, 2, 3, 3]

Output: true
```

  

**Example 2:**

```java
Input: nums = [1, 2, 3, 4]

Output: false
```

**Constraints:**

- `0 <= nums.length <= 10^5`
- `-10^9 <= nums[i] <= 10^9`

## Reasoning
___
The first thing we could  get the urge to do is to brute force it by taking each number a time and search all the way through the list for its duplicate. That would return us an O(n²) time and space complexity, that is a valid way to solve it, but it definitely doesn't scale well.

I decided to do it this way: first, i create a temporary hashset, then i search recursively for the list and for each index, i check if that index' value is already on the hashset, i return true and end the program. Else, i add it to the temp hashset and continue the search.

## What i Learned
___
**Hashset:** Data structure that stores unique elements. It is more efficient for search and operations with its elements.

## Resolution
___
> [!warning]- Spoiler: Resolution
> ## Resolution
> Paste your code below. This box is closed by default and will only show the content when you click the arrow to expand it.
> 
> ```python
> class Solution:
>     def hasDuplicate(self, nums: List[int]) -> bool:
>         hashset = set()
> 
>         for n in nums:
>             if n in hashset:
>                 return True
>             else:
>                 hashset.add(n)
>         return False
> ```