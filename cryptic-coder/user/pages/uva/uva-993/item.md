---
title: 'UVA-993 (Product of digit)'
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
#include<stdio.h>
#include<math.h>
#include<vector>
#include<iostream>
#include<string>
#include<algorithm>
using namespace std;

typedef vector<int> VI;

int main()
{
    int TC, tc;
    int input, minQ;
    VI ans;

    cin >> TC;


    while(TC--) {
        cin >> input;
        if(input < 10) {
            cout << input << "\n";
            continue;
        }

        if(ans.size() != 0) ans.clear();
        for(int i=9; i>=2; i--) {
            if(input % i == 0) {
                ans.push_back(i);
                input /= i;
            }
        }

        if(input != 1) {                            // Means not found.
            cout << "-1\n";
            continue;
        }

        minQ = 0;
        for(int i=0; i<ans.size(); i++) {
            minQ += ( pow(10.0, (double)i) * ans[i] );
        }


        cout << minQ << "\n";

    }

    return 0;
}
```