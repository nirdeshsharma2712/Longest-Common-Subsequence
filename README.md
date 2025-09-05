# 📊 LeetCode Problem: Longest Common Subsequence

## 🧩 Problem Statement

Given two strings `text1` and `text2`, return the length of their **longest common subsequence**. If there is no common subsequence, return `0`.
A subsequence of a string is a new string generated from the original string with some characters (can be none) deleted without changing the relative order of the remaining characters.
**For example**, `"ace"` is a **subsequence** of `"abcde"`.


> **Note :**
> - A common subsequence of two strings is a subsequence that is common to both strings.



## 🧠 Approach: Dynamic Programming – Bottom Up

- We solve it using a `2D DP` **table** where:

- `dp[i][j]` = length of LCS between `s1[0...i-1]` and `s2[0...j-1]`.

- **Initialize** a dp table of size `(n+1) x (m+1)` with `0`.

> **Traverse** both strings:
> - If characters match -> `dp[i][j] = 1 + dp[i-1][j-1]`.
> - Else -> `dp[i][j] = max(dp[i-1][j], dp[i][j-1])`.

- Final **answer** will be in `dp[n][m]`.



## ✅ Example Walkthrough

### Example 1

##### Input: text1 = "abcde", text2 = "ace" 
##### Output: 3

##### Explanation: 
<pre> 
  - The longest common subsequence is "ace" and its length is 3.
  
</pre>

### Example 2

##### Input: text1 = "abc", text2 = "abc"
##### Output: 3

##### Explanation: 
<pre>
  - The longest common subsequence is "abc" and its length is 3.
  
</pre>

### Example 3

##### Input: text1 = "abc", text2 = "def"
##### Output: 0 

##### Explanation: 
<pre>
  - There is no such common subsequence, so the result is 0.
  
</pre>

## 🛠️ Constraints

- `1 <= text1.length, text2.length <= 1000`
- `text1` and `text2` consist of only lowercase English characters.
