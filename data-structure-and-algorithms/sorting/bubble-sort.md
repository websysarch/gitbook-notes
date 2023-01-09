---
description: Array Sorting Algorithm
---

# Bubble Sort

At each iteration the maximum(for asc)/minimum(for desc), is bubbled to the top position i.e. the highest index.

```typescript
export function bubbleSort(array: number[]): number[] {
    let isSorted = false
    let counter = 0
    while(!isSorted) {
        isSorted = true
        for(let i = 0; i < array.length - 1 - counter; i ++) {
            if(array[i] > array[i + 1]) {
                swap(array, i, i+1)
                isSorted = false
            }
        }
        counter += 1
    }
    return array
}

function swap(array: number[], i: number, j: number) {
    const temp = array[j]
    array[j] = array[i]
    array[i] = temp
}
```

#### Using Comparator method

* If >= 0 (Positive Integer), Swap them
* If < 0(Negative Integer/Number), Don't swap them

For Number, ascending order &#x20;

```typescript
function comparator(a: number,b: number): number {
  return a >= b ? 1 : -1 // equivalent to `return a-b`
}
const shouldSwap = (array: number[], a: number, b: number) => comparator(array[a],array[b]) > 0

const swapItem = (array: number[], a: number, b: number) => {
  const temp = array[a]
  array[a] = array[b]
  array[b] = temp
}
export function bubbleSort(array: number[]) {
  const N = array.length
  for(let i = N - 1; i >= 0; i-=1) {
    let hasSwapped = false
    for(let j = 0; j <= i; j+=1) {
      if(shouldSwap(array, j , j + 1)) {
        hasSwapped = true
        swapItem(array, j, j + 1)
      }
    }
    if(!hasSwapped) break;
  }
  return array;
}

```
