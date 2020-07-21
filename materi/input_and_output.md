## Input and Output

Understanding input and output in CP is really important, especially when there are a lot of inputs, and also some unusual inputs. In this section, we will discuss how to do proper basic input and output in C++ for CP.

### Basic inputs

There are usually two ways to take input, the first one is to use `scanf` and the second is to use `cin`. The former is usually faster, but a little bit slower to code, and you have to know what type of input you want to take. Here is an example of inputs using `scanf`:

```c++
int n;
long long m;
string s;

scanf("%d", &n);
scanf("%lld", &m);
scanf("%s", &s);

// you could also do scanf("%d %lld %s", &n, &m, &s);
```

The second way of taking input is to use `cin`, which is faster to type, and you don’t need to know what type of input you want to take. But, it is slower than `scanf` in taking inputs. To solve this, you need the first 3 lines in the template explained before (especially the second line). With those 3 lines, `cin` is now faster. Here is an example of inputs using `cin`:

```c++
int n; // integer
long long m; // long integer
string s; // 

cin >> n >> m >> s;

// you could also do it separately
// cin >> n;
// cin >> m;
// cin >> s;
```

And then, sometimes you need to get a line of input. You can do that input like this:

```c++
string str;
getline(cin, str); // gets all the line in the input

stringstream ss(str);
string token;
while (ss >> token) // useful to take tokens in the line of the input
    cout << token << '\n';
```

Also, there is some problem which doesn't tell you the specific number of inputs. So you can do your inputs like this:

```c++
some_type inp;
while (cin >> inp) {
    solve();
}
```

To test this efficiently, you need to make the `.exe` of your program, which you can do like this:

`g++ -o name_of_program name_of_program.cpp`

And then you can make an `input.in` file with inputs written on it, and then run the program in terminal like this:

`./name_of_program.exe < input.in`

### Basic Outputs

There are also two common ways to output in C++. The first one is to use `printf` and the second one is to use `cout`. This is similar to the two common ways of taking inputs. Here is an example using both of them:

```c++
int n = 1;
long long m = 5
string s = "foobar";

printf("%d %lld %s\n", n, m, s); // prints 1 5 foobar

cout << n << " " << m << " " << s << " " << '\n'; // prints 1 5 foobar
```

For decimal number, you can output it like this:

```c++
// prints with 9 decimal digit
double num;
printf("%.9f", num);
cout << fixed << setprecision(9) << num << '\n';

```

**Remember** to include the first 3 lines in the template to speed up output using `cout`.

### Common Mistakes

Now, there is a common mistake which beginners usually made. When printing an endline, don’t use `endl`, and always use `'\n'`, because it is faster and doesn't flush the output. An exception of this would be in interactive problem, and so you can use `endl`.


Here is an illustration:

```c++
cout << answer << endl; // bad
cout << answer << '\n'; // good
```

Also, when there are many test cases you can output it directly without having to seperately store it first, and then output it in the end.

```c++
// Good Example
for (auto test : testcases) {
    cout << result << '\n';
}

// Bad Example
for (auto test : testcases)
    answer[test] = result;

for (auto test : testcases)
    cout << answer[test] << '\n';
```
