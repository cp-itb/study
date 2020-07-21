## Template for Competitive Programming

There are a lot of templates that you can use, it’s up to you really. But, usually there is a common template that many competitive programmers use.
Which is:

```c++
#include <bits/stdc++.h>

using namespace std;

int main() { 
    ios_base::sync_with_stdio(0);
    cin.tie(0);
    cout.tie(0);


    return 0;
}
```

The first line on that template includes all the necessary stuff you might need (such as algorithms, math, etc). Then the first 3 *magic* lines in the main function is to speed up input and output when using `cin` and `cout`.

This may be called the basic template, so you could add some more if you want to, for an example:

```c++
#include <bits/stdc++.h>

using namespace std;

#define FOR(a, b) for (int i = (int) a; i < (int) b; i++)
#define pb push_back
#define mp make_pair
typedef long long ll;
typedef pair<int, int> pii;

int main() { 
    ios_base::sync_with_stdio(0);
    cin.tie(0);
    cout.tie(0);


    return 0;
}
```