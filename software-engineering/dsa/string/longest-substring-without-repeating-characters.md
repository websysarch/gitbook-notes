# Longest Substring Without Repeating Characters

[Leet Code #3: Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/)

### Problem

Given a string `s`, find the length of the **longest substring** without repeating characters.

&#x20;

**Example 1:**

```
Input: s = "abcabcbb"
Output: 3
Explanation: The answer is "abc", with the length of 3.
```

**Example 2:**

```
Input: s = "bbbbb"
Output: 1
Explanation: The answer is "b", with the length of 1.
```

**Example 3:**

```
Input: s = "pwwkew"
Output: 3
Explanation: The answer is "wke", with the length of 3.
Notice that the answer must be a substring, "pwke" is a subsequence and not a substring.
```

&#x20;

**Constraints:**

* `0 <= s.length <= 5 * 104`
* `s` consists of English letters, digits, symbols and spaces.

### Hints

* Use Sliding Window Approach

### Solution

#### Solution

* Time Complexity: `O(n)`
* Space Complexity: `O(n)`

```typescript
function lengthOfLongestSubstring(str: string): number {
    let maxLength = 0
    let windowStartIdx = 0
    const charLastIdxCache = new Array(128)
    for(let windowEndIdx = 0; windowEndIdx < str.length; windowEndIdx += 1) {
        const cacheKey = str.charCodeAt(windowEndIdx)
        if(charLastIdxCache[cacheKey] >= windowStartIdx) {
            windowStartIdx = charLastIdxCache[cacheKey] + 1
        } else {
            maxLength = Math.max(maxLength, windowEndIdx - windowStartIdx + 1)
        }
        charLastIdxCache[cacheKey] = windowEndIdx
    }
    return maxLength
};
```
