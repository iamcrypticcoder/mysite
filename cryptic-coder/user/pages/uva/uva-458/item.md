---
title: 'UVA-458 (The Decoder)'
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
#include<string.h>


int main()
{
	char coded[200];
	int i;

	while(gets(coded)) {
	for(i = 0; i < strlen(coded); i++)
		printf("%c", coded[i] - 7);
	printf("\n");
	}
return 0;
}
```