---
title: 'UVA-10300 (Ecological Premium)'
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
	int tc, TC;
	long long numFarmer, size, noAnimal, degree, ans;

	cin >> TC;

	while(TC--) {
		cin >> numFarmer;

		ans = 0;
		while(numFarmer--) {
			cin >> size >> noAnimal >> degree;
			ans += (size * degree);
		}
		cout << ans << endl;

	}

	return 0;
}
```