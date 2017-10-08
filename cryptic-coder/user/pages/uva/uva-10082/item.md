---
title: 'UVA-10082 (WERTYU)'
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
#include <cstring>

using namespace std;


char table[100] = "`1234567890-=	QWERTYUIOP[]ASDFGHJKL;'ZXCVBNM,./";

int main()
{
	char input[100];
	int i, j;
	int Is_Capital;

	
	
	while(gets(input)) {

	for(i=0; i<strlen(input); i++) {
		if(input[i] == ' ') { cout << input[i]; continue; }
		
		for(j=0;j<47; j++) 
			if(input[i] == table[j]) {
			cout << table[j-1];
				break;
			}
	}
	cout << "\n";
	}
return 0;
}
```