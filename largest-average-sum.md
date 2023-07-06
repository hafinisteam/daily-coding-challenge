### Problem
```
Given a list of numbers and a number k, return whether any two numbers from the list add up to k.
For example, given [10, 15, 3, 7] and k of 17, return true since 10 + 7 is 17.
```
### Solution

```
1. Get initial window sum
2. Max sum = initial window sum
3. Loop over array number while moving the window
4. At every iteration remove left window element and add right window element to get max sum
5. Return max sum divide by k
```

### Code
```
const largestAverageWindow = (arr, k) => {
  let start = 0;
  let end = k - 1;
  let maxSum = 0;
  let windowSum = arr.slice(0, k).reduce((prev, current) => prev + current, 0);

  while (end < arr.length - 1) {
    windowSum -= arr[start];
    start++;
    end++;
    windowSum += arr[end];
    maxSum = Math.max(maxSum, windowSum);
  }
  return maxSum / k;
};
```

Link: [https://codesandbox.io/s/two-sum-t5sh65](https://codesandbox.io/s/largest-average-window-4xv74w)https://codesandbox.io/s/largest-average-window-4xv74w
