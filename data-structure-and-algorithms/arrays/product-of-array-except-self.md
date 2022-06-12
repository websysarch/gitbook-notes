# Product of Array Except Self

[Leet Code #238: Product of Array Except Self](https://leetcode.com/problems/product-of-array-except-self/)

### Problem Statement

Given an integer array `nums`, return _an array_ `answer` _such that_ `answer[i]` _is equal to the product of all the elements of_ `nums` _except_ `nums[i]`.

The product of any prefix or suffix of `nums` is **guaranteed** to fit in a **32-bit** integer.

You must write an algorithm that runs in `O(n)` time and without using the division operation.

&#x20;

**Example 1:**

```
Input: nums = [1,2,3,4]
Output: [24,12,8,6]
```

**Example 2:**

```
Input: nums = [-1,1,0,-3,3]
Output: [0,0,9,0,0]
```

&#x20;

**Constraints:**

* `2 <= nums.length <= 105`
* `-30 <= nums[i] <= 30`
* The product of any prefix or suffix of `nums` is **guaranteed** to fit in a **32-bit** integer.



**Follow up:** Can you solve the problem in `O(1)` extra space complexity? (The output array **does not** count as extra space for space complexity analysis.)

### Hints

### Solution

#### Solution  With O(1) space

```typescript
function productExceptSelf(nums: number[]): number[] {
    const output = nums.map(n => 1)
    let product = 1
    
    for(let i = 0; i < nums.length; i+= 1) {
        output[i] *= product
        product *= nums[i]
    }
    
    product = 1
    for(let i = nums.length - 1; i >= 0; i -= 1) {
        output[i] *= product
        product *= nums[i]
    }
    
    return output
};
```

#### Solution with O(n) space

```typescript
function productExceptSelf(nums: number[]): number[] {
    const productLeft = (new Array(nums.length)).fill(1)
    const productRight = (new Array(nums.length)).fill(1)
    
    for(let i = 1; i < nums.length; i+=1) {
        productLeft[i] = productLeft[i - 1] * nums[i -1]
    }
    for(let i = nums.length - 2; i >= 0; i-=1) {
        productRight[i] = productRight[i + 1] * nums[i + 1]
    }
    const output = new Array(nums.length)
    for(let i = 0; i < nums.length; i+= 1) {
        output[i] = productRight[i] * productLeft[i]
    }
    console.log(productLeft)
    console.log(productRight)
    return output
};
```
