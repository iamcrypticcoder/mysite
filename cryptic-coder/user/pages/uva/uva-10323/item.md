---
title: 'UVA-10323 (Factorial You Must be Kidding)'
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

using namespace std;


double fact(int num)
{
	if (num == 1) return 1;
	else return (num*fact(num-1));
}

void Process(int n)
{
	if(!(n % 2)) cout << "Underflow!\n";
	else cout << "Overflow!\n";
}


int main()
{
	int input;
	double ans;

	while(cin >> input) {
		if(input < 0) 
			Process(input);
		else if(input > 13) 
			cout << "Overflow!\n";
		else if(input < 8) 
			cout << "Underflow!\n";
		else 
			printf("%.0lf\n", fact(input));
	}
return 0;
}
```