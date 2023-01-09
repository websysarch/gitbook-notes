# Longest Palindromic Substring

[Leetcode #5: Longest Palindromic Substring](https://leetcode.com/problems/longest-palindromic-substring/)

### Problem Statement

Given a string `s`, return _the longest palindromic substring_ in `s`.

**Example 1:**

```
Input: s = "babad"
Output: "bab"
Explanation: "aba" is also a valid answer.
```

**Example 2:**

```
Input: s = "cbbd"
Output: "bb"
```

&#x20;

**Constraints:**

* `1 <= s.length <= 1000`
* `s` consist of only digits and English letters.

### Solutions

#### Solution 1: Expand Around middle

* Time - O(`n^2`)
* Space - O(1)

```typescript

function longestPalindrome(s: string): string {
    let si = 0
    let ml = 1
    function expandAroundMiddle(l, r) {
        for(;l >= 0 && r < s.length && s[l] === s[r]; l-=1, r+=1 ){
            const cl = r - l + 1
            if(ml < cl) {
                ml = cl
                si = l
            }
        }
    }
    
    for(let i = 0; i <= s.length;i+=1) {
        expandAroundMiddle(i, i+1) // For Odd 
        expandAroundMiddle(i-1, i+1) // Accounts for Even palindrome
    }
    return s.substring(si, si+ml)
};
```
