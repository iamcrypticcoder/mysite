---
title: 'UVA-10195 (The Knights Of The Round Table)'
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
#include <set>
#include <map>

using namespace std;


typedef vector<int> VI;
typedef vector<double> VD;
typedef vector<string> VS;
typedef long long LL;

#define FOR(i, L, U)		for(int i=L; i<=U; i++)
#define EPS 1e-9


double a, b, c;


int main()
{
	double ans, s;

	while(cin >> a >> b >> c) {
		s = (a+b+c)/2;

        if(a==0 || b == 0 || c == 0) ans = 0.000;
		else ans = sqrt((s-a)*(s-b)*(s-c)/s);
	//	cout.precision(3);
	    printf("The radius of the round table is: %.3lf\n", ans);
//		cout << "The radius of the round table is: " << ans << "\n";
	}

	return 0;
}
```