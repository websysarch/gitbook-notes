# Coin Change

[Leet Code #322: Coin Change](https://leetcode.com/problems/coin-change/)

### Problem Statement

You are given an integer array `coins` representing coins of different denominations and an integer `amount` representing a total amount of money.

Return _the fewest number of coins that you need to make up that amount_. If that amount of money cannot be made up by any combination of the coins, return `-1`.

You may assume that you have an infinite number of each kind of coin.

&#x20;

**Example 1:**

```
Input: coins = [1,2,5], amount = 11
Output: 3
Explanation: 11 = 5 + 5 + 1
```

**Example 2:**

```
Input: coins = [2], amount = 3
Output: -1
```

**Example 3:**

```
Input: coins = [1], amount = 0
Output: 0
```

&#x20;

**Constraints:**

* `1 <= coins.length <= 12`
* `1 <= coins[i] <= 231 - 1`
* `0 <= amount <= 104`

### Solution

* Time Complexity: O(amount X no of coins)
* Space Complexity: O(amount)

```typescript
function coinChange(coins: number[], amount: number): number {
    const dpCache = (new Array(amount + 1)).fill(amount+1) // min coin is 1, so amount + 1 is the max num
    dpCache[0] = 0
    
    for(let a = 1; a <= amount; a += 1) {
        for(const coin of coins) {
            if(a >= coin) {
                dpCache[a] = Math.min(
                    1 + dpCache[a - coin],
                    dpCache[a]
                )   
            }
        }
    }
    return dpCache[amount] === amount + 1 ?  - 1 : dpCache[amount]
};
```
