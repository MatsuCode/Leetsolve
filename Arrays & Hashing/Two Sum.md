---
tags:
  - ArraysAndHashing
date: 2026-09-29
---
## Problem
___
Given an array of integers `nums` and an integer `target`, return the indices `i` and `j` such that `nums[i] + nums[j] == target` and `i != j`.

You may assume that _every_ input has exactly one pair of indices `i` and `j` that satisfy the condition.

Return the answer with the smaller index first.

**Example 1:**

```java
Input: 
nums = [3,4,5,6], target = 7

Output: [0,1]
```

Explanation: `nums[0] + nums[1] == 7`, so we return `[0, 1]`.

**Example 2:**

```java
Input: nums = [4,5,6], target = 10

Output: [0,2]
```

**Example 3:**

```java
Input: nums = [5,5], target = 10

Output: [0,1]
```

**Constraints:**

- `2 <= nums.length <= 1000`
- `-10,000,000 <= nums[i] <= 10,000,000`
- `-10,000,000 <= target <= 10,000,000`
- **Only one valid answer exists.**
## Reasoning
___
The easiest way to solve this case did not really fit my needs, i'm gonna tell you why.

You can just look for all the list for a number, and then do it again to find the other one, but again, this is an O(n²) approach. What that means?

The amount of calls to this code will be always around the number of itens on the list mutiplied by itself. It means that if this list has 2 itens, it would have 4 calls, but to 12 numbers, the code calls are around 144. The focus here is to not let the calls scale with the code, so i thought about an alternative.

it is unavoidable to make at least more than a single call to the code to get the answer, so i decided to eliminate the second round of calls by following this steps:

1. Get a number;
2. Find out how much it needs to get to the target;
3. If the number is on the list, we found the answer, if not, go to the next one and repeat.
## What i Learned
___
**Synthax:** Python lets you find out if a number is in a list easily using:
```python
if n in nums:
```

That alone lets you get an smaller amount of resource usage with less loop functions to find simple data.

## Resolution
___
> [!warning]- Spoiler: Resolution
> ## Resolution
> Paste your code below. This box is closed by default and will only show the content when you click the arrow to expand it.
> 
> ```python
> class Solution:
>    def twoSum(self, nums: List[int], target: int) -> List[int]:
>        for i in range(len(nums)):
>            if target - nums[i] in nums and nums.index(target - nums[i]) != i:
>                return sorted([i, nums.index(target - nums[i])])
> ```