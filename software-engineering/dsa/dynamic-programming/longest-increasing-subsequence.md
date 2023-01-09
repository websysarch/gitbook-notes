# 🟠 Longest Increasing Subsequence

[Leet Code #300: Longest Increasing Sub-Sequence](https://leetcode.com/problems/longest-increasing-subsequence/)

### Problem Statement

Given an integer array `nums`, return the length of the longest strictly increasing subsequence.

A **subsequence** is a sequence that can be derived from an array by deleting some or no elements without changing the order of the remaining elements. For example, `[3,6,2,7]` is a subsequence of the array `[0,3,1,6,2,2,7]`.

&#x20;

**Example 1:**

```
Input: nums = [10,9,2,5,3,7,101,18]
Output: 4
Explanation: The longest increasing subsequence is [2,3,7,101], therefore the length is 4.
```

**Example 2:**

```
Input: nums = [0,1,0,3,2,3]
Output: 4
```

**Example 3:**

```
Input: nums = [7,7,7,7,7,7,7]
Output: 1
```

&#x20;

**Constraints:**

* `1 <= nums.length <= 2500`
* `-104 <= nums[i] <= 104`

&#x20;

**Follow up:** Can you come up with an algorithm that runs in `O(n log(n))` time complexity?

### Hints

* For `O( n log n)`, we need greedy solution using binary search

### Solutions

#### Recursion

* Time Complexity: O(n^2)
* Space Complexity: O(n)

```typescript
function lengthOfLIS(nums: number[]): number {
    const N = nums.length
    const cache = (new Array(N)).fill(1)
    for(let j = 1; j < N; j+=1) {
        for(let i = 0; i <= j; i+=1) {
            if(nums[i] < nums[j]) {
                cache[j] = Math.max(
                    1 + cache[i],
                    cache[j]
                )
            }
        }
    }
    console.log(cache)
    return Math.max(...cache)
};
```

