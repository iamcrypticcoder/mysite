---
title: 'UVA-10127 (Ones)'
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
	unsigned long INPUT, rem=1, num_of_one=1, Dividend=1;

	
	while(cin >> INPUT) {
		rem=1; num_of_one=1; Dividend=1;
		for(;;) {
			if(Dividend < INPUT) {
				Dividend = Dividend*10 +1;
				num_of_one++;
			}
			rem = Dividend % INPUT;
			if(rem == 0) break;
			else Dividend = rem;
		}

		cout << num_of_one << "\n";
	}
return 0;
}
```