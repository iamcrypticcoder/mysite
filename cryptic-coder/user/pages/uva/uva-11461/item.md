---
title: 'UVA-11461 (Square Numbers)'
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
#include <iostream>
#include <math.h>

using namespace std;

int main()
{
    int a, b;

    while(cin >> a >> b) {
        if(a == 0 && b == 0) break;

        a = (int)ceil(sqrt(a));
        b = (int)floor(sqrt(b));

        cout << b - a + 1 << "\n";
    }

    return 0;
}
```