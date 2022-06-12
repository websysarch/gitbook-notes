# Max Sub Array

[Leet Code: #56: Maximum Sub Array](https://leetcode.com/problems/maximum-subarray/)

### Problem Statement

Given an integer array `nums`, find the contiguous subarray (containing at least one number) which has the largest sum and return _its sum_.

A **subarray** is a **contiguous** part of an array.

&#x20;

**Example 1:**

```
Input: nums = [-2,1,-3,4,-1,2,1,-5,4]
Output: 6
Explanation: [4,-1,2,1] has the largest sum = 6.
```

**Example 2:**

```
Input: nums = [1]
Output: 1
```

**Example 3:**

```
Input: nums = [5,4,-1,7,8]
Output: 23
```

&#x20;

**Constraints:**

* `1 <= nums.length <= 105`
* `-104 <= nums[i] <= 104`

&#x20;

**Follow up:** If you have figured out the `O(n)` solution, try coding another solution using the **divide and conquer** approach, which is more subtle.

### Solution

#### Solution using Divide & Concur

#### Solution using DP

* Time Complexity: Linear
* Space Complexity: Constant

```typescript
function maxSubArray(nums: number[]): number {
    let currMax = nums[0]
    let lastMax = nums[0]
    for(let i=1; i < nums.length; i++) {
        lastMax = Math.max(
            lastMax + nums[i],
            nums[i]
            )
        currMax = Math.max(currMax, lastMax)
    }
    return currMax
}
```

