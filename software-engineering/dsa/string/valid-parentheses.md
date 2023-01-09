# Valid Parentheses

[Leet Code #20 Valid Parentheses](https://leetcode.com/problems/valid-parentheses/)

### Problem

Given a string `s` containing just the characters `'('`, `')'`, `'{'`, `'}'`, `'['` and `']'`, determine if the input string is valid.

An input string is valid if:

1. Open brackets must be closed by the same type of brackets.
2. Open brackets must be closed in the correct order.

&#x20;

**Example 1:**

```
Input: s = "()"
Output: true
```

**Example 2:**

```
Input: s = "()[]{}"
Output: true
```

**Example 3:**

```
Input: s = "(]"
Output: false
```

&#x20;

**Constraints:**

* `1 <= s.length <= 104`
* `s` consists of parentheses only `'()[]{}'`.

### Hints

* If its odd, its invalid
* Use Stack for parsing
* &#x20;At anytime, if stack.length > remaining string, its invalid

### Solution

#### Solution Using Map

* Time Complexity: O(n)
* Space Complexity: O(n)

```typescript
function isValid(s: string): boolean {
    if(s.length % 2) return false // If its odd, its invalid
    const stack = []
    const map = {'(': ')','{': '}','[': ']'}
    for(let i = 0; i < s.length; i+=1) {
        const char = s[i]
        if(map[char]) {
            stack.push(char)
        } else {
            if(map[stack.pop()] !== char) return false
        }
    }
    return stack.length == 0
};
```

#### Solution

* Time Complexity: O(n)
* Space Complexity: O(n)

```typescript
function isValid(s: string): boolean {
    if(s.length % 2) return false // If its odd, its invalid
    const stack = []
    const N = s.length
    for(let i = 0; i < N && stack.length <= N -i; i+=1) {
        const char = s[i]
        if(char === '(' || char === '{' || char === '[') {
            stack.push(char)
        } else {
            const openingBracket = stack.pop()
            if(openingBracket === undefined) return false
            if(
                (openingBracket === '(' && char === ')') ||
                (openingBracket === '{' && char === '}') ||
                (openingBracket === '[' && char === ']') 
            ) {continue;}
            return false
        }
    }
    return stack.length == 0
};
```
