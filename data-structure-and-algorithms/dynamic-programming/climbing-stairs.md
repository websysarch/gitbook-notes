# Climbing Stairs

[LeetCode #70: Climbing Stairs](https://leetcode.com/problems/climbing-stairs/)

### Problem

You are climbing a staircase. It takes `n` steps to reach the top.

Each time you can either climb `1` or `2` steps. In how many distinct ways can you climb to the top?

&#x20;

**Example 1:**

```
Input: n = 2
Output: 2
Explanation: There are two ways to climb to the top.
1. 1 step + 1 step
2. 2 steps
```

**Example 2:**

```
Input: n = 3
Output: 3
Explanation: There are three ways to climb to the top.
1. 1 step + 1 step + 1 step
2. 1 step + 2 steps
3. 2 steps + 1 step
```

&#x20;

**Constraints:**

* `1 <= n <= 45`

### Hints

* This basically creates a pattern similar to fibonacci series. Where,&#x20;
  * n1 = 1
  * n2 = 2
  * n(x) = n(x-1) + n(x-2)



### Solution

#### Solution: Iterative

Caching is not required, since it maintains last two

* Tme Complexity: O(n)
* Space Complexity: O(1)

```typescript
function climbStairs(n: number): number {
    if(n <= 2) return n
    let n1 = 1
    let n2 = 2
    for(let i = 3; i <= n; i+=1) {
        let t = n1 + n2
        n1 = n2
        n2 = t
    }
    return n2
}
```

#### Solution: Recursive with caching

* Tme Complexity: O(n)
* Space Complexity: O(n)

```typescript
const cache = {}
function climbStairs(n: number): number {
    if(n <= 2) return n    
    if(cache[n]) return cache[n]
    const res = climbStairs(n - 1) + climbStairs(n - 2)
    cache[n] = res
    return res
};
```
