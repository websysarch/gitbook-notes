# Unique Paths

[Leet Code #62: Unique Paths](https://leetcode.com/problems/unique-paths/)

### Problem Statement



There is a robot on an `m x n` grid. The robot is initially located at the **top-left corner** (i.e., `grid[0][0]`). The robot tries to move to the **bottom-right corner** (i.e., `grid[m - 1][n - 1]`). The robot can only move either down or right at any point in time.

Given the two integers `m` and `n`, return _the number of possible unique paths that the robot can take to reach the bottom-right corner_.

The test cases are generated so that the answer will be less than or equal to `2 * 109`.

&#x20;

**Example 1:**

![Robote Maze](broken-reference)

```
Input: m = 3, n = 7
Output: 28
```

**Example 2:**

```
Input: m = 3, n = 2
Output: 3
Explanation: From the top-left corner, there are a total of 3 ways to reach the bottom-right corner:
1. Right -> Down -> Down
2. Down -> Down -> Right
3. Down -> Right -> Down
```

&#x20;

**Constraints:**

* `1 <= m, n <= 100`

### Solutions

#### Iterative

```typescript
function getCache(m: number, n: number): number[][] {
    const cache = new Array(m)
    cache[0] = (new Array(n)).fill(1)
    for(let i = 1; i <= m; i+=1) {
        cache[i] = (new Array(n)).fill(0)
        cache[i][0] = 1
    }
    return cache
}
function uniquePaths(m: number, n: number): number {
    if(m === 1 || n === 1) return 1
    const cache = getCache(m, n)
    for(let i = 1; i < m; i+=1) {
        for(let j = 1; j < n; j+=1) {
            cache[i][j] = cache[i-1][j] + cache[i][j-1]
        }
    }
    return cache[m-1][n-1]
};
```

#### Recursive

```typescript
function getCache(m, n) {
    const cache = new Array(m + 1)
    cache[0] = (new Array(n+1)).fill(1)
    for(let i = 1; i <= m; i+=1) {
        cache[i] = (new Array(n+1)).fill(0)
        cache[i][0] = 1
    }
    return cache
}
function uniquePaths(m: number, n: number, cache = getCache(m, n)): number {
    if(n === 1 || m === 1) return 1
    if(cache[m][n]) return cache[m][n]
    const res = uniquePaths(m-1, n, cache) + uniquePaths(m, n-1, cache)
    cache[m][n] = res
    return res
};
```
