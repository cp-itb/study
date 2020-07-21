## Fast Exponential

Fast exponential is a useful technique which is frequently used in competitive programming. It is basically a faster approach to finding $x^y$ (where $y$ is a non-negative integer).

Here is the implementation:

```c++
int fastexpo(int x, int y) {
    int result = 1;
    while (y > 1) {
        if (y % 2 == 1) {
            result = result * x;
        }
        y /= 2;
        x = x * x;
    }
    return result;
}
```

An alternative implementation would be:

```c++
int fastexpo(int x, int y) {
	if (y == 0) return 1;
	int temp = fastexpo(x, y / 2);
	temp = temp * temp;
	if (y % 2 == 1) temp = temp * a;
	return temp;
}
```

## Modulo

Answers to a CP problem often are too big to handle in programming languages. Usually, we only need to output the answer by a modulo $p$ (where $p$ is a prime number). Modulo is basically a residual quotient, you can see the details [here](https://brilliant.org/wiki/modular-arithmetic/).

In C++ and many other languages, we can use modulo with `%`. We will see how we handle modulo in programming, here is an example:

```c++
// Basic operation
a = (a % p); // gets value of a modulo p
a = ((a % p) + p) % p; // Handles when a is negative

// Addition
res = (a + b) % p;
res = ((a % p) + (b % p)) % p;

// Subtraction
res = (a - b) % p; // res can still be negative
res = ((a % p) - (b % p)) % p; // res can also still be negative
res = (res % p + p) % p; // use this, to make res non-negative

// Multiplication
res = (a * b) % p; // not a good approach
res = ((a % p) * (b % p)) % p; // a safer approach
```

## Inverse Modulo

Inverse modulo is useful to handle modulo when there are divisions in place. You can see the full explanation [here](https://cp-algorithms.com/algebra/module-inverse.html).