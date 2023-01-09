# Valid Anagram

Given two strings `s` and `t`, return `true` _if_ `t` _is an anagram of_ `s`_, and_ `false` _otherwise_.

An **Anagram** is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

&#x20;

**Example 1:**

```
Input: s = "anagram", t = "nagaram"
Output: true
```

**Example 2:**

```
Input: s = "rat", t = "car"
Output: false
```

&#x20;

**Constraints:**

* `1 <= s.length, t.length <= 5 * 104`
* `s` and `t` consist of lowercase English letters.

&#x20;

**Follow up:** What if the inputs contain Unicode characters? How would you adapt your solution to such a case?

### Solution

* Time Complexity: Linear
* Space Complexity: Constant (since 26 chars only)

```typescript
function isAnagram(s: string, t: string): boolean {
    if(s.length !== t.length) return false
    const charCountMap = {}
    for(let char of s) {
        charCountMap[char] = (charCountMap[char] + 1) || 1
    }
    for(let char of t) {
        if(!charCountMap[char]) return false
        charCountMap[char] -= 1
    }
    return true
};
```
