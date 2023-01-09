# Group Anagrams

[Leet Code #49: Group Anagrams](https://leetcode.com/problems/group-anagrams/)

### Problem

Given an array of strings `strs`, group **the anagrams** together. You can return the answer in **any order**.

An **Anagram** is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

&#x20;

**Example 1:**

```
Input: strs = ["eat","tea","tan","ate","nat","bat"]
Output: [["bat"],["nat","tan"],["ate","eat","tea"]]
```

**Example 2:**

```
Input: strs = [""]
Output: [[""]]
```

**Example 3:**

```
Input: strs = ["a"]
Output: [["a"]]
```

&#x20;

**Constraints:**

* `1 <= strs.length <= 104`
* `0 <= strs[i].length <= 100`
* `strs[i]` consists of lowercase English letters.

### Hints

### Solution

#### Using Map

* Time Complexity: O(`n*`m`*log_m`), O(n,m)&#x20;
  * n = size of string array
  * m = size of individual string
* Space Complexity: O(n\*m) // for each string, you need a copy of re-arranged string as key

```typescript
function groupAnagrams(strs: string[]): string[][] {
    if(strs.length == 0) return [strs];
    let m = new Map();
    strs.forEach((word) => { // O(n)
        let a = word.split("").sort().join(""); // O(m*log_m)
        m.has(a) ? m.get(a).push(word) : m.set(a, [word]);
    })
    return Array.from(m.values());
};
```

#### Using Custom HashKey

* Time Complexity: O(n), O(n,m)&#x20;
  * n = size of string array
  * m = size of individual string
* Space Complexity: O(1)

```typescript
/*
* getHashKey(string): hashKey
* HashKey is concatanation of repetitions of those char.
* eg: "ABBC", `1,2,1,,,,<26chars>`
*/
function getHashKey(str: string): string { // O(m), size: Constant:26chars(log_10_m)
    const charMap = new Array() // Max 28 size
    for(let i = 0; i < str.length; i+=1) {
        const k = str.charCodeAt(i) - 97
        charMap[k] = (charMap[k] || 0) + 1
    }
    return charMap.join()
}

/**
* Returns map of numeric Ids (incremented) corresponding to each
* string, based on the hashKey.
*/
function getSimplifiedKey(strs: string[]) { // O(nxm)
    const hashKeyIdMap = {}
    let autoId = 1
    return strs.map((str, idx) => { // O(n)
        const k = getHashKey(str) // O(m)
        if(!hashKeyIdMap[k]) {
            hashKeyIdMap[k] = ++autoId
        }
        return hashKeyIdMap[k]
    }) 
}

function groupAnagrams(strs: string[]): string[][] {
    const strKeys =  getSimplifiedKey(strs) // O(nxm)
    const output: Record<string, string[]> = {}
    for(let i = 0; i < strs.length; i+=1) { // O(n)
        if(output[strKeys[i]]) {
            output[strKeys[i]].push(strs[i])
        } else {
            output[strKeys[i]] = [strs[i]]
        }
    }
    return Object.values(output)
};
```
