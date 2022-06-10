---
description: Sorting  Algorithms
---

# Sorting

#### Parameters to evaluate a sorting algorithm

| Features           | Notes                                                                           |
| ------------------ | ------------------------------------------------------------------------------- |
| Time Complexity    |                                                                                 |
| Spacial Complexity |                                                                                 |
| Stability          | If two values are equal for sorting comparisons, their order must be preserved. |

### Selection Sort



### Bubble Sort

> Time Complexity: O(`n^2`), \
> Space Complexity: O(1)
>
> Stable

```javascript
function bubbleSort(nums, compFun = (a, b) => a - b) {
  let hasSwapped;
  let iter = 0;
  do {
    hasSwapped = false;
    iter += 1;
    for (let i = 0; i < nums.length - iter; i += 1) {
      if (compFun(nums[i], nums[i + 1]) >= 1) {
        const t = nums[i];
        nums[i] = nums[i + 1];
        nums[i + 1] = t;
        hasSwapped = true;
      }
    }
  } while (hasSwapped);
  return nums;
}
```

### Selection Sort

### Insertion Sort
