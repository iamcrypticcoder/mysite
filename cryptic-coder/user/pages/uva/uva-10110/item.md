---
title: 'UVA-10110 (Light more light)'
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
#include <cmath>

using namespace std;



int main()
{
	unsigned int input, k;

	while(cin >> input && input != 0) {
		k = (unsigned int)sqrt(input);
		if(k*k == input)
			cout << "yes\n";
		else 
			cout << "no\n";
	}
}
```