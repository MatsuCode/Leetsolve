---
tags:
  - python
date: 2026-09-28
---
## Problem
___
Given two strings `s` and `t`, return `true` if the two strings are anagrams of each other, otherwise return `false`.

Two strings are **anagrams** if they contain the same characters, with each character appearing the same number of times, regardless of order.

  

**Example 1:**

```java
Input: s = "racecar", t = "carrace"

Output: true
```

  

**Example 2:**

```java
Input: s = "jar", t = "jam"

Output: false
```

  

**Example 3:**

```java
Input: s = "x", t = "x"

Output: true
```

  

**Constraints:**

- `1 <= s.length, t.length <= 5 * 10^4`
- `s` and `t` consist of lowercase English letters.
## Reasoning
___
This problem wants you to recognize if two different words are anagrams. But what's an anagram?

We learned in grammar that "anagram" is what we call two words that are composed by the exact same letter, in a way that you can reorganize them to get the exact same word as the other one.

With that in mind, i looked for the following approach:
1. Reorganize the characters on both words the same way;
2. Check if the results are equal each other.

to get to that result, the easiest way i could find was alphabetic order, so i used a string reordering algorithm to treat all the characters of the word like individual itens in a list.

```java
boxes -> [b, o, x, e, s]
```

Now, you might know that the common latin alphabet has 26 letters. Each one has its specific index. So, if you take this letters as theirs respective indexes, you're gonna have:

```java
[b, o, x, e, s] -> [2, 15, 24, 5, 19]
```

After i understood that, i simply reordened them using a function that reorders strings by the index of each character and compared both.
## What i Learned
___
**Sortering and Ordering:** Each programming language has its own way to deal with strings. sorting, reversing, modifying and more. You gotta understood how that's made in the language you chose to learn.

## Resolution
___
> [!warning]- Spoiler: Resolution
> ## Resolution
> Paste your code below. This box is closed by default and will only show the content when you click the arrow to expand it.
> ```python
> class Solution:
>	def isAnagram(self, s: str, t: str) -> bool:
>        firstWord = sorted(s)
>        secondWord = sorted(t)
>        
>        return firstWord == secondWord
> ```
