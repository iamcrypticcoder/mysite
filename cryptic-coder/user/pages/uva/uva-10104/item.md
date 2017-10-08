---
title: 'UVA-10104 (Euclid Problem)'
published: true
date: '00:05 11/02/2016'
taxonomy:
    category:
        - blog
    tag:
        - uva
body_classes: 'header-lite fullwidth blogstyling'
---

Here is full code:

===

```cpp
#include <stdio.h>
#include <iostream>

using namespace std;

int x, y, g;
void ext_gcd(int a, int b)
{
    if( b == 0) {
        x = 1; y = 0; g = a; return;
    }
    ext_gcd(b, a%b);
    int x1 = y;
    int y1 = x - (a/b)*y;
    x = x1;
    y = y1;
}

int main()
{
    int a, b;
    int gcd;

    while(cin >> a >> b) {
        ext_gcd(a, b);

        printf("%d %d %d\n", x, y , g);
    }

    return 0;
}
```