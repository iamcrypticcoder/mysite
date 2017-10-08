---
title: 'UVA-10165 (Stone Game)'
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

using namespace std;

#define FOR( i, L, U ) for(int i=(int)L ; i<=(int)U ; i++ )
#define FORD( i, U, L ) for(int i=(int)U ; i>=(int)L ; i-- )

int main()
{
    int N, temp;

    while(cin >> N) {
        if(N == 0) break;
        int XOR = 0;
        FOR(i, 1, N) {
            cin >> temp;
            XOR ^= temp;
        }

        if(XOR == 0)
            cout << "No\n";
        else cout << "Yes\n";


    }
    return 0;
}
```