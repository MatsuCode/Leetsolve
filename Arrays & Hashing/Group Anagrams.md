---
tags:
  - ArraysAndHashing
date: 2026-09-28
---
## Problem
___
Medium Topics Company Tags Hints

Given an array of strings `strs`, group all _anagrams_ together into sublists. You may return the output in **any order**.

An **anagram** is a string that contains the exact same characters as another string, but the order of the characters can be different.

**Example 1:**

```java
Input: strs = ["act","pots","tops","cat","stop","hat"]

Output: [["hat"],["act", "cat"],["stop", "pots", "tops"]]
```

**Example 2:**

```java
Input: strs = ["x"]

Output: [["x"]]
```

**Example 3:**

```java
Input: strs = [""]

Output: [[""]]
```

**Constraints:**

- `1 <= strs.length <= 10000`.
- `0 <= strs[i].length <= 100`
- `strs[i]` is made up of lowercase English letters.`

## Reasoning
___
The definition of an "anagram" is essentialy two or more words that share the same word count. For example:

```
anagrams = ["tea", "eat"]
```

Anagrams[0] has 1t, 1e and 1a, the same as "eat", but in other order. This can be used to identify them, counting for each word how much of each letter it has and grouping them with the others.

So this was my approach:
1. Made a dict to store all the arrays;
2. For each word in the list i made a list of 26 zeros, so we can track how many times each letter appears in the word;
3. And for each character in that string, i add +1  in the index that represents the order of that letter on the list;

```python
ord("a") # 97

ord(character) - ord("a") # if character == "a", ord("a") - ord("a") = 0
```

4. Then we turn the count into a valid key to the dict;
5. and put the word in that list.
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
>class Solution:
>    def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
>        res = defaultdict(list)
>
>        for s in strs:
>            count = [0] * 26
>            for c in s:
>                count[ord(c) - ord("a")] += 1
>            res[tuple(count)].append(s)
>
>        return list(res.values())
> ```