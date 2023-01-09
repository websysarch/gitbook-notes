# Three Sum

[Leet Code #15: 3sum](https://leetcode.com/problems/3sum/)

### Problem Statement

Given an integer array nums, return all the triplets `[nums[i], nums[j], nums[k]]` such that `i != j`, `i != k`, and `j != k`, and `nums[i] + nums[j] + nums[k] == 0`.

Notice that the solution set must not contain duplicate triplets.

&#x20;

**Example 1:**

```
Input: nums = [-1,0,1,2,-1,-4]
Output: [[-1,-1,2],[-1,0,1]]
```

**Example 2:**

```
Input: nums = []
Output: []
```

**Example 3:**

```
Input: nums = [0]
Output: []
```

&#x20;

**Constraints:**

* `0 <= nums.length <= 3000`
* `-105 <= nums[i] <= 105`

### Solution

#### Solution

* Time Complexity: Quadratic
* Space Complexity: Constant

```typescript
function threeSum(nums: number[]): number[][] {
    const N = nums.length
    nums.sort((a,b) => a-b)
    const res = []
    for(let i = 0; i < N - 2; i++) {
        const target = 0 - nums[i]
        let left = i + 1
        let right = N - 1
        if(i > 0 && nums[i] === nums[i - 1]) {
            continue
        }
        while(left < right) {
            const lrs = nums[left] + nums[right]
            if(lrs === target) {
                res.push([nums[i], nums[left], nums[right]])
                left++
                while(nums[left] === nums[left - 1]) {
                    left++
                }
            } else if(lrs < target) {
                left++
            } else {
                right--
            }
        }
    }
    return res
}
```

#### &#x20;Solution:  Extending 2 num sum with additional loop

* Time Complexity: Quadratic
* Space Complexity: Linear

```typescript
function threeSum(nums: number[]): number[][] {
    const N = nums.length
    const output = []
    const keySet = new Set()
    for(let i = 0; i < N - 2; i+=1){
        const cache = new Set()
        const target = 0 - nums[i]
        for(let j = i + 1; j < N; j+=1) {
            if(cache.has(target - nums[j])) {
                const triplet = [nums[i], nums[j], target - nums[j]].sort()
                const key = triplet.join('_')
                if(!keySet.has(key)) {
                    output.push(triplet)
                    keySet.add(key)
                }
            } else {
                cache.add(nums[j])
            }
        }
    }
    return output
};
```
