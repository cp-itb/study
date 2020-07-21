## Searching and Sorting
### Sorting

Sorting can be said as one of the most important things to know when starting cp. There are many well-known sorting algorithms out there. 
Lucky for you, to sort a sequence in C++, you don’t have to make your own code.

In this tutorial we are going to use array and vector.

The standard way to sort in C++ is using the standard library. The standard library of sorting have time complexity of $O(N \log N)$

#### Sorting to a non-decreasing order

On array with index $[0, \dots, n - 1]$

```c++
sort(ar, ar + n);
```

On array with index $[1, \dots, m]$

```c++
sort(ar + 1, ar + m + 1);
```

on vector

```c++
sort(vec.begin(), vec.end());
```

Example:

```c++
int ar[4] = {5, 3, 100, 1};
sort(ar + 1, ar + 4);
for (int i = 0; i < 4; i++) cout << ar[i] << “ “; // output is “5 1 3 100”
// notice that we were sorting the elements on indexes [1, 3]
```

#### sorting to a non-increasing order

Example:

```c++
int ar[4] = {5, 3, 100, 1};
sort(ar + 1, ar + 4, greater<int>());
for (int i = 0; i < 4; i++) cout << ar[i] << “ “; // output is “5 100 3 1”
// notice that we were sorting the elements on indexes [1, 3]

long long ar2[5] = {5, 3, 100, 1, 10};
sort(ar2, ar2 + 5, greater<long long>());
for (int i= 0 ; i < 5; i++) cout << ar2[i] << “ “; // output is “100 10 5 3 1”
```

#### sorting with a custom comparison

*Example*

```c++
#include <bits/stdc++.h>

using namespace std;

pair<int, int> ar[5];

bool custom_compare(const pair<int, int>& a, const pair<int, int>& b){
	return a.second < b.second;
}

int main() {
	ios_base::sync_with_stdio(0);
	cin.tie(0);
	cout.tie(0);

	ar[0] = make_pair(70, 123);
	ar[1] = make_pair(5, 12);
	ar[2] = make_pair(44, 88);
	ar[3] = make_pair(43, 1);
	ar[4] = make_pair(51, 1200);

	sort(ar, ar + 5, custom_compare);
	for (int i = 0; i < 5; i++){
		cout << ar[i].first << " " << ar[i].second << '\n';
	}
	/*
	output:
	43 1
	5 12
	44 88
	70 123
	51 1200

	notice that we sort the element according to the second attribute
	*/

	// You can also do it like this
	sort(ar, ar + 5, [&](auto a, auto b) {
		return a.second < b.second;
	});

	return 0;
}
```

## Searching

The most naive searching algorithm is linear search. In this algorithm, you basically only need to iterate over all the elements.

```c++
// linear search, searching element k inside ar
bool found = false;
for (auto x : ar) {
	if (x == k) {
		found = true;
		break;
	}
}
```

Using linear search would result in a $O(N)$ of time complexity per searching. 

Other than linear search, there are other searching algorithms. One of the most commonly used is binary search. To execute binary search inside an array, you need to have the array sorted first.

The idea behind binary search is to half the searching area in every iteration. Using this idea, you can achieve time complexity of $O(\log N)$ (If it's already sorted).

```c++
// binary search, finding element k in an array ar

sort(ar, ar + n); // sort the array if the array isn’t sorted yet

int low = 0, high = n - 1;
bool found = false;
while (low <= high) {
	int mid = (low + high) / 2;
	if (ar[mid] >= k) {
		high = mid - 1; // halve the searching area
		if (ar[mid] == k) {
			found = true;
			break;
		}
	} else {
		low = mid + 1; // halve the searching area
	}
}
```

If you are given an unordered array, using a binary search algorithm would require you to sort the elements first, resulting in a $O(N \log N)$ time complexity, knowing that fact, you have to remember that you only needed to do the sorting once. 

After the array is sorted, you can perform an arbitrary number of searches in only $O(\log N)$ time complexity per search.


Other than to search an element, you can also use binary search to search for an answer (usually called “binary search the answer”).

One such example is for searching a square root of a number:

```c++
// binary search, finding square root of n
const double eps = 1e-9;

double l = 0, r = n, res = -1;
while (r - l > e) {
    double mid = (l + r) / 2.0;
    if (mid * mid <= n) {
        l = mid;
        res = mid;
    } else {
        r = mid;
    }
}
```

Binary search is very useful in CP, so we recommend you to see a video lecture [here](https://codeforces.com/blog/entry/67509).
