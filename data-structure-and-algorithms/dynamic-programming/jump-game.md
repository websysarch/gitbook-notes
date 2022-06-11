# Jump Game

[Leet Code #55: Jump Game](https://leetcode.com/problems/jump-game/)

### Problem



You are given an integer array `nums`. You are initially positioned at the array's **first index**, and each element in the array represents your maximum jump length at that position.

Return `true` _if you can reach the last index, or_ `false` _otherwise_.

&#x20;

**Example 1:**

```
Input: nums = [2,3,1,1,4]
Output: true
Explanation: Jump 1 step from index 0 to 1, then 3 steps to the last index.
```

**Example 2:**

```
Input: nums = [3,2,1,0,4]
Output: false
Explanation: You will always arrive at index 3 no matter what. Its maximum jump length is 0, which makes it impossible to reach the last index.
```

&#x20;

**Constraints:**

* `1 <= nums.length <= 104`
* `0 <= nums[i] <= 105`

### Hints

### Solution

* Time Complexity: Linear O(n)
* Space Complexity: Constant O(1)

```typescript
function canJump(nums: number[]): boolean {
    if(nums.length === 0) return true
    if(nums.length === 1 && nums[0] > 0) return true
    let li = 0
    for(let i = 1; i < nums.length && i <= li + nums[li]; i+=1) {
        if(nums[i] > (nums[li] - i + li)) {
            li = i
            if(nums[li] + li >= nums.length - 1) return true
        }
    }
    if(nums[li] + li >= nums.length - 1) return true
    return false
};
```

