## Dynamic Programming

Dynamic Programming is an algorithm design technique to find an optimal solution of a problem or to count how many possibilities of something to occur. 

Dynamic Programming can be seen as an optimization method that uses memory to store an answer of recursions call. With the stored answer, you don’t need to execute the function call again and then can save some time with that later.

One such example is to use dynamic programming for finding a fibonacci sequence.

A fibonacci sequence can be defined as:

$$ F_n = F_{n-1} + F_{n-2} $$

notice that if you want to find the $N$-th fibonacci sequence, chances are you need to call some functions multiple times.

For instance, calling fibbonaci($6$), is depicted as the following:

![fibonacci](./images/fib.png)

If you do it naively, you will have a time complexity of $O(2^N)$, which is very slow.

To handle this problem, you can simply store the answer of the function call and then get the result of the function call immediately later.

When implementing dynamic programming, there are 2 different ways, which is top-down and bottom-up.

### Top-down fibonacci

```c++
long long dp[N];
void initialize() {
	fill(dp, dp + N, -1);
	dp[0] = 0; dp[1] = 1;
}

long long fibonacci(int n) {
	if (dp[n] != -1) return dp[n];
	dp[n] = fibonacci(n - 1) + fibonacci(n - 2);
	return dp[n];
}
```

### Bottom-up fibonacci

```c++
long long fibonacci(int n){
	long long dp[N];
	dp[0] = 0; dp[1] = 1;
	for (int i = 2; i <= n; i++) {
        dp[i] = dp[i - 1] + dp[i - 2];
	}
	return dp[n];
}
```

This implementation will have a time complexity of $O(N)$, which is way faster.

While the bottom-up dynamic programming is shorter to code and have a faster run-time most of the time, to get the idea of a bottom-up solution sometimes would be harder.

### Finding Longest Common Subsequence of 2 Strings

Statement: Given 2 strings $S$ and $T$, find the longest common subsequence of them. 

A subsequence is a sequence that can be constructed by taking elements from the original sequence without changing the order.

*For Example*, Given string $S = "\text{ABCDE}"$, strings “$\text{CE}$”, “$\text{ABD}$”, “$\text{BC}$” is a subsequence of string $S$, While strings “$\text{ADB}$”, “$\text{CB}$”, “$\text{EA}$” is not.

#### Top-down implementation

```c++
string s;
string t;

int dp[N][N];
void initialize() {
	int n = s.length();
	int m = t.length();
	for (int i = 0; i < n;i++) {
        for (int j = 0; j < m; j++) {
            dp[i][j] = -1;
        }
	}
}

int LCS(int i, int j) {
	if (i == -1 || j == -1) return 0;
	if (dp[i][j] != -1) return dp[i][j];
	if (s[i] == t[j]) {
    	   dp[i][j] = max(dp[i][j], LCS(i - 1, j - 1) + 1);
	}
	dp[i][j] = max(dp[i][j], max(LCS(i - 1, j), LCS(i, j - 1)));
	return dp[i][j];
}
```


#### Bottom-up implementation

```c++
int LCS(const string& s, const string& t) {
	int n = s.length();
	int m = t.length();
	int dp[n][m];
	for (int i = 1; i < n; i++){
    	for (int j = 1; j < m; j++){
        	dp[i][j] = -1;
    	}
	}
	for (int i = 0; i < n; i++){
    	dp[i][0] = s[i] == t[0];
	}
	for (int i = 0; i < m; i++){
    	dp[0][i] = s[0] == t[i];
	}
	for (int i = 1; i < n; i++){
    	for (int j = 1; j < m; j++){
        	if (s[i] == t[j]) dp[i][j] = max(dp[i][j], dp[i - 1][j - 1] + 1);
        	dp[i][j] = max(dp[i][j], max(dp[i - 1][j], dp[i][j - 1]));
    	}
	}
	return dp[n - 1][m - 1];
}
```
