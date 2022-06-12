# Two Sum

[LC #1: Two Sum](https://leetcode.com/problems/two-sum/)

### Problem Statement

Given an array of integers `nums` and an integer `target`, return _indices of the two numbers such that they add up to `target`_.

You may assume that each input would have _**exactly**_** one solution**, and you may not use the _same_ element twice.

You can return the answer in any order.

&#x20;

**Example 1:**

```
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
```

**Example 2:**

```
Input: nums = [3,2,4], target = 6
Output: [1,2]
```

**Example 3:**

```
Input: nums = [3,3], target = 6
Output: [0,1]
```

&#x20;

**Constraints:**

* `2 <= nums.length <= 104`
* `-109 <= nums[i] <= 109`
* `-109 <= target <= 109`
* **Only one valid answer exists.**

&#x20;

**Follow-up:** Can you come up with an algorithm that is less than `O(n2)` time complexity?

### Solution

* Time Complexity: Linear
* Space Complexity: Linear

#### Solution

```typescript
function twoSum(nums: number[], target: number): number[] {
    const map = {}
    for(let i = 0; i <= nums.length; i+=1) {
        const num = nums[i]
        const reqNum = target - num
        if(map[reqNum] !== undefined) {
            return [i, map[reqNum]]
        } else {
            map[num] = i
        }
    }
    return [-1, -1]
};
```

