## Prefix and Suffix Sum

Prefix and suffix sum is a technique that is useful to handle subarray sums.

To build a prefix sum array, you are required to precompute the sum of the prefix and store it inside of an array.

### Building a prefix sum array

```c++
ar[1] = 20; ar[2] = 12; ar[3] = 17;
ar[4] = 99; ar[5] = 51;

// build a prefix sum array
for (int i = 1; i <= 5; i++) {
	pre[i] = pre[i - 1] + ar[i];
}
// elements of ar  = {0, 20, 12, 17, 99, 51, ...}
// elements of pre = {0, 20, 32, 49, 148, 199, ...}
```

To build a suffix sum array is similar to a prefix sum array, instead of iterating from the first index, you can simply start iterating from the last index.

```c++
for (int i = 5; i >= 1; i--) {
	suf[i] = suf[i + 1] + ar[i];
}
```

A simple application of prefix sum is for finding a sum of element inside a range. for instance, if the array is indexed in range $[1,10]$, to find the sum of elements in the range of $[3,8]$ you can simply compute `pre[8] - pre[3 - 1]`.

More formally, to find the sum of elements in range $[L, R]$ you can compute it with `pre[R] - pre[L - 1]`.

Another application of prefix sum is for finding a maximum sum of a subarray, but will not be further discussed here.
