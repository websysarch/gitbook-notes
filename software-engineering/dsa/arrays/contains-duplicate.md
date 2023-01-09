# Contains Duplicate

[Leet Code #217: Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)

### Problem Statement



Given an integer array `nums`, return `true` if any value appears **at least twice** in the array, and return `false` if every element is distinct.

&#x20;

**Example 1:**

```
Input: nums = [1,2,3,1]
Output: true
```

**Example 2:**

```
Input: nums = [1,2,3,4]
Output: false
```

**Example 3:**

```
Input: nums = [1,1,1,3,3,4,3,2,4,2]
Output: true
```

&#x20;

**Constraints:**

* `1 <= nums.length <= 105`
* `-109 <= nums[i] <= 109`

### Solutions

#### Using Set

* Time Complexity: Linear O(n)
* Space Complexity: Linear O(n)

```typescript
function containsDuplicate(nums: number[]): boolean {
    const hasAppeared= new Set()
    for(let num of nums) {
        if(hasAppeared.has(num)) return true
        hasAppeared.add(num)
    }
    return false
};
```
