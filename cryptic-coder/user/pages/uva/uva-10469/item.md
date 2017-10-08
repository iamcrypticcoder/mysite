---
title: 'UVA-10469 (To Carry or not to Carry)'
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
#include <vector>
#include <cmath>

using namespace std;

int main()
{
	unsigned int num1, num2, result;

	while(cin >> num1 >> num2) {
		result = num1 ^ num2;
		cout << result << "\n";
	}
	return 0;
}
```