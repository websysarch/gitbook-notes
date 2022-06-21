# Binary Search

* When the array is sorted, and you need to find something, which could be compared, eg. numbers.

### Recursive

* Time Complexity: `O( log n)`
* Space Complexity: `O ( log n)`

```typescript
function binarySearchUtil(array: number[], target: number, startIdx: number = 0, endIdx: number = array.length - 1): number {
  if(startIdx > endIdx) return -1
  const midIdx = Math.floor((startIdx + endIdx) / 2)
  const midNum = array[midIdx]
  if(midNum === target) return midIdx
  if(target < midNum) return binarySearchUtil(array, target, startIdx, midIdx - 1)
  return binarySearchUtil(array, target, midIdx + 1, endIdx)
}
```

### Iterative

* Time Complexity: `O(log n)`
* Space Complexity: Constant

```typescript
export function binarySearch(array: number[], target: number): number {
  let start = 0
  let end = array.length - 1
  while(start <= end) {
    const mid = Math.floor((start + end) / 2)
    const midValue = array[mid]
    if(target === midValue) return mid
    if(target < midValue) {
      end = mid - 1
    } else {
      start = mid + 1
    }
  }
  return -1
}
```
