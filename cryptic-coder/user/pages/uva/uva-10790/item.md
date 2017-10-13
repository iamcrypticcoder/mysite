---
title: 'UVA-10790 (How Many Points of Intersection)'
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
#include <cstdio>
#include <cmath>
#include <iostream>

using namespace std;



int main()
{
	long long a,b, ans;
	int tc;

	for(tc = 1; cin >> a >> b && a != 0 && b != 0; tc++)
	{
		ans = ( a*(a-1) ) / 2;
		ans *= ( ( b*(b-1) ) / 2 );

		cout << "Case " << tc << ": "; 
		cout << ans << "\n";

	}

	return 0;
}
```