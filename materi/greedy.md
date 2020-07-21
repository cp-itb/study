## Greedy

Greedy is an algorithmic paradigm that builds up a solution piece by piece, always choosing the next piece that offers the most obvious and immediate benefit. So the problems where choosing locally optimal also leads to global solution are best fit for Greedy.

For an example, this problems is a best fit for greedy:

### Maximizing Pairs

Given two lists of integers, both have the size of $N$, which is a positive integer. You need to make $N$ pairs of integers, every pair consists of an element from the first list and an element of the second list. And then for every pair $(a, b)$ you need to multiply it and add it to the result. Of all the possible pairs, find the maximum result you can get!

Example:

$L_1 = [6, 3, 9, 10]$

$L_2 = [1, 3, 7, 2]$

$\text{Result} = 112$

Explanation:
The maximum result we can get is by having:

$\text{pairs} = (10, 7), (9, 3), (6, 2), (3, 1)$

So we would have the maximum result, which is:

$\text{Result} = 10 \times 7 + 9 \times 3 + 6 \times 2 + 3 \times 1 = 112$

### Solution

It’s quite obvious that to have a maximum result, you will need maximum pairs. So the answer to this question is to take the biggest value of the first list and also from the second list. So the greedy approach here is to always take the maximum pair of list every step.

Here is the solution written in C++:

```c++
sort(L1, L1 + n);
sort(L2, L2 + n);
int maximum_result = 0;
for (int i = n - 1; i >= 0; i--)
    maximum_result += L1[i] * L2[i];
cout << maximum_result << '\n';
```

Greedy is often obvious to see, but it doesn't always guarantee a correct answer. So you might use a greedy approach if it can be proven to be the right approach.
