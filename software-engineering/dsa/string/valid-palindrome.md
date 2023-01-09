# Valid Palindrome

### Problem Statement

[Leet code #125](https://leetcode.com/problems/valid-palindrome/)

A phrase is a **palindrome** if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.

Given a string `s`, return `true` _if it is a **palindrome**, or_ `false` _otherwise_.



**Example 1:**

```
Input: s = "A man, a plan, a canal: Panama"
Output: true
Explanation: "amanaplanacanalpanama" is a palindrome.
```

**Example 2:**

```
Input: s = "race a car"
Output: false
Explanation: "raceacar" is not a palindrome.
```

**Example 3:**

```
Input: s = " "
Output: true
Explanation: s is an empty string "" after removing non-alphanumeric characters.
Since an empty string reads the same forward and backward, it is a palindrome.
```

&#x20;

**Constraints:**

* `1 <= s.length <= 2 * 105`
* `s` consists only of printable ASCII characters.

### Hints

* Only ASCII characters are allowed, so valid codes is `0 <= code <= 128`
* Set the same code for upperCase and lowerCase. distinct for each alpha.
* For looping use two pointers, one from start and another from end.

### Solutions

#### Solution using Regex and ToLowerCase

```typescript
function isPalindrome(s: string): boolean {
  s = s.toLowerCase();
  s = s.replace(/[^a-zA-Z0-9]/gi, "");
  for (var i = 0; i < Math.floor(s.length / 2); i++) {
    if (s[i] != s[s.length - i - 1]) return false;
  }
  return true;
}
```

#### Solution - Without using Regex Or ToLowerCase

```typescript
function generateCache() {
    const cache = new Array(128) // Everything is undefined.
    for(let i = 0; i <= 9; i+=1) {
        cache[i + 48] = i + 48
    }
    for(let i = 0; i < 26; i+=1) {
        cache[i + 65] = i + 97
        cache[i + 97] = i + 97
    }
    return cache
}
const cache = generateCache()

function isPalindrome(s: string): boolean {    
    let start = 0
    let end = s.length - 1
    while(start < end) {
        if(!cache[s.charCodeAt(start)]) {
            start += 1
            continue
        }
        if(!cache[s.charCodeAt(end)]) {
            end -= 1
            continue
        }
        if(cache[s.charCodeAt(start)] === cache[s.charCodeAt(end)]) {
            start += 1
            end -= 1
        } else {
            return false
        }
    }
    
    return true
};
```
