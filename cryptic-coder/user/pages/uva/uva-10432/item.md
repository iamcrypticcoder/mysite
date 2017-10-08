---
title: 'UVA-10432 (Polygon Inside A Circle)'
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
#include <math.h>

#define PI 2*acos(0.0)

int main()
{
 double n, r;
 double result;

// printf("%0.10lf" , 2*acos(0.0));

 cout << PI;
 while(scanf("%lf %lf", &r, &n) != EOF && n>2 && n<20000 && r>0 && r<20000) {
  result = n*0.5*r*r*sin((2*PI)/n);
  printf("%.3lf\n", result);
 }
 return 0;
}
```