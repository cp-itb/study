## Bruteforce

Usually there are problems that are straightforward and could be solved using bruteforce.

The most basic example is to use a layer of for loops. Say we want to find all 3 positive integers $a$, $b$, and $c$, such that $a + b + c = 10$. Then we can solve it by using bruteforce like this:

```c++
for (int a = 1; a <= 10; a++) {
    for (int b = 1; b <= 10; b++) {
        for (int c = 1; c <= 10; c++) {
            if (a + b + c == 10)
                cout << a << " " << b << " " << c << '\n';
        }
    }
}
```

This of course results in a large time complexity so using bruteforce is usually bad, but when it can be used, it is usually safer and more precise.

### Permutations

Now suppose we want to find all permutations of an array, then we can use a built-in library in C++, to do that. Here is the example:

```c++
int a[5] = {1, 2, 3, 4, 5};
do {
    for (int i = 0; i < 5; i++) {
        cout << a[i] << ' ';
    }
    cout << '\n';
} while (next_permutation(a, a + 5));
```
 
**Note**: You need to have the array sorted first, if you want to see all it’s permutations.

### Finding all subset

If you want to find all subset in an array, you can use the following technique:

```c++
int n = 5;
int a[n] = {1, 2, 3, 4, 5};
for (int mask = 0; mask < (1 << n); mask++) {
    for (int i = 0; i < n; i++) {
        if (mask & (1 << i)) {
            cout << i << ' ';
        }
    }
    cout << '\n';
}
```

This is related to bit operations. You can search on google if you want to know how this works.

### Enumerating All Subset of Size K

If you want to find all subset having sized K, you can do it with this magic trick:

```c++
vector<int> v(n, 1);
for (int i = 0; i < k; i++) {
    v[i] = 0;
}
do {
    for (int i = 0; i < n; i++) {
        if (v[i] == 1) continue;
        // do stuff with it's element
    }
} while (next_permutation(v.begin(), v.end()));
```