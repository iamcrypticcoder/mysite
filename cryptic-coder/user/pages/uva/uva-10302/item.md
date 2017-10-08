---
title: 'UVA-10302 (Summation of Polynomials)'
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
#include <cstdio>
#include <cmath>
#include <iostream>
#include <vector>
#include <list>
#include <stack>
#include <queue>
#include <string>
#include <algorithm>

using namespace std;


typedef vector<int> VI;
typedef vector<double> VD;
typedef vector<string> VS;

#define SQR(x) ((x)*(x))

int main()
{
	long long n;


	while(cin >> n) 
	{
		cout << SQR((n*(n+1))/2) << endl;
	
	}

	return 0;
}
```