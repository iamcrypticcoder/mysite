---
title: 'UVA-10071 (Back to High School Physics)'
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
#include <string.h>
#include <stdlib.h>

int main()
{
	int v=5, t=12;
	double a, s;
	
	while(scanf("%d %d", &v, &t)!= EOF) {
		if(t == 0) {
			printf("0\n");
			continue;
		}
		a = (double) v/t;

		s = v*t + a * (t*t);

		printf("%.0lf\n", s);
	}

return 0;
}
```