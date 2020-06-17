# Starting Competitive Programming

Ever wanted to try and compete on Competitive Programming (CP)? Is it hard for you to find a way on how to start? Don't worry! we'll guide you on how to start CP, starting from the basics, so let's get started!

---

# Table of Contents
- [What is Competitive Programming?](#What-is-Competitive-Programming?)
- [Problem Example](#Problem-Example)
- [Setting Up Competitive Programming Tools](#Setting-Up-Competitive-Programming-Tools)
- [Code Example](#Code-Example)
- [Platforms to Study Competitive Programming](#Platforms-to-Study-Competitive-Programming)
- [Awesome Resources to Start](#Awesome-Resources-to-Start)

---

## What is Competitive Programming?

Competitive Programming is a mind sport programming where participants are given a problem and have to solve the problem by making an efficient program under the given constraint. Usually, the program is made with programming languages such as C++, Java, or Python, but it depends on the contest and platform.

---

## Problem Example

Almost all competitive programming problems have the same format, it will have the problem name, problem description, the constraint of the problem, format input and output examples, explanation (not always), and also the time and memory limit for the program solution. Here is the problem example:

### **Pair of Tens!**

**Time Limit**: 1s

**Memory Limit**: 64MB

Given a list of **n** integer numbers, **a_1, a_2, ..., a_n**. Find the number of pairs in the list which adds up to 10.

**Input**

The first line of input contains one integer **n** (2 <= **n** <= 1000), which is the number of integer in the list.

The second line contains n integers, the i-th of them is **a_i** (0 <= **a_i** <= 10), which is the value of the i-th integer in the list.

**Output**

Print a single line containing the number of pairs in the list which adds up to 10.

**Examples**

Input:
```
5
3 7 2 8 8
```
Output:
```
3
```

Input:
```
4
5 5 5 5
```
Output:
```
6
```

**Explanation**

On the first example, there is 3 pair which adds up to 10, that is (3, 7), (2, 8), and also (2, 8). Note that numbers having the same value can be counted more than once.

---

If you are already familiar with the basics of programming, then you might have an idea of how to solve that problem, but we will go through it later.

---

## Setting Up Competitive Programming Tools

In order to start your competitive programming journey, you will need the right tools. There are basically only two tools you need in your computer, which is an IDE/Code Editor and An Installed Programming Language. Now, you might choose any of those tools to your heart content, but I recommend you to follow along this tools.

### IDE/Code Editor

The first tool is the IDE/Code Editor, which is basically the environment you're going to use to program. There are tons of awesome IDEs, but I recommend using **Visual Studio Code**, because honestly it is one of the best IDE right now and almost everyone is using it. You could go install it [here](https://code.visualstudio.com/).


### Programming Language

When it comes to CP, C++ is by far the most widely used language. This is mainly because C++ have a lot of great template library and it is faster than other languages. You could see a detailed instruction to install C++ right [here](https://www.tutorialspoint.com/cplusplus/cpp_environment_setup.htm).

After you install those two tools, you could also install extensions on visual studio code to help you code, I recommend you to install the extension [C/C+++ Compile Run](https://marketplace.visualstudio.com/items?itemName=danielpinto8zz6.c-cpp-compile-run) so you could run and compile the code by just clicking F6. You could also find other extensions yourself if you'd like.

---

## Code Example

Now let's begin to solve the previous given problem. If you are new to programming, don't worry, you only need to know the basics which is if-else statements, loops, and functions. One of the easiest solution for the problem is to choose two different elements (not necessarily different element value) in the list, and so we could use two for-loops and try every pair in the list. Here is the code written in C++:

```c++
#include <iostream>

using namespace std;

int main() {
    // Take inputs
    int n;
    cin >> n;
    int a[n];
    for (int i = 0; i < n; i++) {
        cin >> a[i];
    }
    int answer = 0;
    // Try every pair
    for (int i = 0; i < n - 1; i++) {
        for (int j = i + 1; j < n; j++) {
            // If this pair adds up to 10, then increment answer
            if (a[i] + a[j] == 10) {
                answer++;
            }
        }
    }
    cout << answer << endl;

    return 0;
}
```

Notice that it will take n * (n + 1) / 2 operations, because the maximum n is 1000, and so we'll have approximately 500500 operations which will take comfortably under 1 second, and so this is a valid solution for the given constraints. However, this is actually not a good solution, and most competitive programming problems actually has a more tight constraint, in this case, what if n is bigger than 1000? say 1000000, then it will definitely consume a lot of operations and run time, and so it will take more than 1 second to finish.

This is actually what makes competitive programming different, you have to not only make a program to solve the problem, but also to find a way to make the program run fast and efficient. Now, it is definitely good to learn this bruteforces techniques first to get you started, and so along the way, you will eventually gain more knowledge to solve problems more efficiently.

In comparison, this is one of the better solution, which is to use **hashmap**, here is the code:

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    ios_base::sync_with_stdio(0);
    cin.tie(0);
    cout.tie(0);

    int n;
    cin >> n;
    unordered_map<int, int> mp;
    int answer = 0;
    for (int i = 0; i < n; i++) {
        int x;
        cin >> x;
        answer += mp[x - 10];
        mp[x]++;
    }
    cout << answer << '\n';

    return 0;
}
```

Now if you don't understand the better solution yet, it's definitely ok, just keep in mind that by learning competitive programming, you will have the skills to make a great, fast and efficient program.

---

## Platforms to Study Competitive Programming

When it comes to platforms in learning competitive programming, there are a lot of good platforms. And so, I recommend these 4 platforms to start, which is [TLX](https://tlx.toki.id/), [CodeForces](https://codeforces.com/), [AtCoder](https://atcoder.jp/), and [HackerRank](https://www.hackerrank.com/).

### TLX

[TLX](https://tlx.toki.id/) is a competitive programming platform from Indonesia made by TOKI. And If you are new to programming, this is the best website to start. TLX gives a good course for you to start on programming and also the basics of competitive programming (not yet available other than in indonesian language). You could try the course [here](https://tlx.toki.id/courses).

### CodeForces

[CodeForces](https://codeforces.com/) is the biggest platform to use for learning competitive programming, it has the most active users, with many problems, weekly contest, and also editorials/solution you could see. I actually have made a blog about codeforces which you could see [here](https://cp-itb.github.io/blog//codeforces/2020/03/25/Improve-CP-With-Codeforces.html).

### AtCoder

[AtCoder](https://atcoder.jp/) is a competitive programming platform from japan. It has one of the best problems including beginner problems, which could improve your CP skills. And I also recommend for you to participate in AtCoder Beginner Contest which is usually held almost every week there.

### HackerRank

[HackerRank](https://www.hackerrank.com/) is actually more of a site to learn for interview questions, but it's also a good resource to learn competitive programming, especially for beginners. It has a lot of good problems and most importantly it has the solution for the problems, so you could learn better.

There are also other platforms you could learn from, such as [codechef](http://codechef.com/), [kattis](https://open.kattis.com/), [vjudge](http://vjudge.net/), and [SPOJ](http://www.spoj.com/).

---

## Awesome Resources to Start

To end this guide, here is a list of awesome resouces to get you started in competitive programming!

- [What is Competitive Programming - William Lin](https://www.youtube.com/watch?v=ueNT-w7Oluw&t=75s)
- [How to Start Competitive Programming - Errichto](https://www.youtube.com/watch?v=xAeiXy8-9Y8&t=7s)
- [Starting Competitive Programming, Steps and Mistake - William Lin](https://www.youtube.com/watch?v=bVKHRtafgPc)
- [Pemrograman Kompetitif Dasar](https://osn.toki.id/arsip/download-pkd)
- [Introduction to USA Computing Olympiad](http://darrenyao.com/usacobook/cpp.pdf)
- [Competitive Programming Handbook](https://cses.fi/book/book.pdf)
- [Competitive Programming Algorithms](https://cp-algorithms.com/)
- [Fundemental of Algorithms](https://www.geeksforgeeks.org/fundamentals-of-algorithms/)
- [Top Algorithm and Data Structure for Competitive Programming](https://www.geeksforgeeks.org/top-algorithms-and-data-structures-for-competitive-programming/)
- [Other Awesome List for Competitive Programming](https://codeforces.com/blog/entry/23054?mobile=false#tutorial-websites)
