## Standard Template Library

C++ comes with a lot of useful libraries we can use. In this section we will see some of them which are used very often in competitive programming. You can use this by using `#include <bits/stdc++.h>` in the top of your code.

Here are some of STL Algorithms.

```c++
int a[n];

sort(a, a + n); // Sort array of size n
reverse(a, a + n); // Reverse the array
*max_element(a, a + n); // returns the maximum element from 0 to n - 1 in a
*min_element(a, a + n); // returns the minimum element from 0 to n - 1 in a
accumulate(a, a + n, 0); // returns the sum of elements of a

// If a is sorted then you can use this
binary_search(a, a + n, x); // returns whether x is in a or not
lower_bound(a, a + n, x); // returns an iterator to the first element greater or equal to x in a
upper_bound(a, a + n, x); // returns an iterator to the first element greater to x in a

```

There are also a lot of useful built-in data structures, you can use. Here is an example:

```c++
queue<int> q;
q.push(5);
q.push(2);
q.push(3);
// Output it elements : 5 2 3
while (!q.empty()) {
    cout << q.front() << ' ';
    q.pop();
}
cout << '\n';

stack<int> st;
st.push(5);
st.push(2);
st.push(3);
// Output it elements : 3 2 5
while (!st.empty()) {
    cout << st.top() << ' ';
    st.pop();
}
cout << '\n';

vector<int> v;
v.push_back(5);
v.push_back(2);
v.push_back(4);
for (auto& e : v) cout << e << ' ';
cout << '\n';
v.pop_back(); // pops the back of the element if it's not empty

deque<int> dq;
dq.push_back(5);
dq.push_back(2);
dq.push_front(4);
// output the elements in the deque dq : 4 5 2
for (auto& e : dq) cout << e << ‘ ‘;
dq.pop_back(); // pops the back of the element if it's not empty
dq.pop_front(); // pops the front of the element if it's not empty

set<int> s;
s.insert(5);
s.insert(2);
s.insert(5);
s.insert(1);
// output it's size : 3
cout << s.size() << '\n';
// output elements in the set s : 1 2 5
for (auto& e : s) {
   cout << e << ' ';
}
s.find(x); // returns an iterator to the value x if there is x in s, and returns s.end() otherwise
s.lower_bound(x); // returns an iterator to the first element greater or equal to x in s
s.upper_bound(x); // returns an iterator to the first element greater to x in s
s.erase(x); // erase the value x in s if there is any
// note that this set is ordered by the smaller value (default)
// you can change it to larger value with set<int, greater<int>>

unoredered_set<int> us;
us.insert(5);
us.insert(2);
us.insert(5);
us.insert(1);
// output it's size : 3
cout << us.size() << '\n';
// unoredered_set cannot be iterated like set

multiset<int> ms;
ms.insert(5);
ms.insert(2);
ms.insert(5);
ms.insert(1);
// output it's size : 4
cout << ms.size() << '\n';
// output the elements in the multiset ms : 1 2 5 5
for (auto& e : ms) {
   cout << e << ' ';
}
ms.find(x); // returns an iterator to the value x if there is x in ms, and returns ms.end() otherwise
ms.lower_bound(x); // returns an iterator to the first element greater or equal to x in ms
ms.upper_bound(x); // returns an iterator to the first element greater to x in ms
ms.erase(x); // erase all the value x in ms if there is any
ms.erase(ms.find(x)); // erase only one value x in ms if there is any

map<int, int> mp;
mp[5] = 2;
mp[10] = 3;
// output key and value pair
for (auto e : mp) {
    cout << e.first << " " << e.second << '\n';
}
mp.count(x); // equals to zero if x has not yet been a key value and one otherwise

unordered_map<int, int> mp; // cannot be iterated, but faster to use when storing integers
mp[5] = 2;
mp[10] = 3;

priority_queue<int> pq;
pq.push(2);
pq.push(5);
pq.push(3);
// output it's element : 5 3 2
while (!pq.empty()) {
   cout << pq.top() << " ";
   pq.pop();
}
// Note that the default is storing the biggest element in the top
// you can also configure it to smallest element first, by doing
// priority_queue<int, vector<int>, greater<int>>
```

This is only an example, you can find on the internet yourself to know more about how to use the STL in C++. Usually, the best place to see it’s example is to go to [cppreference](https://en.cppreference.com/), or just by simply googling it.