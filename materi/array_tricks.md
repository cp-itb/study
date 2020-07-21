## Array with negative indexes

Sometimes while solving a problem, you will need to use an array with negative indexes. While it is possible to use hash map/map/other data structures, there are simpler and cheaper (in terms of complexity) ways to do this.

Working with negative indexes, the first thing that comes to mind would probably be using some base index. Assuming that the range of indexes would be $-N \leq \text{index} \leq N$, you could use base $N$ to do this.

For instance,

```c++
const int N = some_number;

int ar[2 * N];

// print element at index -2
cout << ar[N + -2];
```

It is a pretty good way to do this. But this is not the best thing you could do. It is easy to forget to add the base index. So what other options are available?

There is actually a better way to do this,

```c++
// const int N = some_number;

int _ar[2 * N];
int * ar = ar + N; // put the array pointer to the base index

// print element at index -2
cout << ar[-2];
```

This trick works because we put the pointer of variable ar to the base index. you could read more about pointer [here](https://en.cppreference.com/w/cpp/language/pointer), or just by simply googling it.