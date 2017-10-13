---
title: 'UVA-11150 (Cola)'
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

int main()
{
	int input = 9, carry;
	int temp;
	int a,b;
	int total;
	int max=0;

	while(cin >> input) {
		max = 0;
	for(carry=0; carry<3; carry++) {
		temp = input+carry;
		total = input;
		for(; temp >= 3;) {
			a = temp % 3;
			b = temp / 3;
			temp = a + b;
			total += b;;
		}
		if( b >= carry && total > max)
			max = total;
	}


	cout << max << "\n";
	//cout << b << "\n";
	}
}
```