---
title: 'UVA-10673 (Play with Floor and Ceil)'
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
//#include <conio.h>
#include <math.h>

int main()
{
	long x, k, p, q;
	long i, j, l;
	long temp1, temp2, temp;
	int Is_break, t_case;

	scanf("%d", &t_case);

	for(l=1; l<=t_case; l++ ) {

		scanf("%ld %ld", &x, &k);

/*		if(!(x%k)) {
			p = k/2;
			q = k/2;
		}
		else {*/
			temp1 = (long)floor((double)x/k);
			temp2 = (long)ceil((double)x/k);
		
			for(i=0; ; i++)
				if((x - temp1*i) % temp2 == 0) {
					p = i;
					q = (x - temp1*p) / temp2;
					break;
				}
		//}
		
		printf("%ld %ld\n", p ,q);
	}

//getch();
return 0;
}
```