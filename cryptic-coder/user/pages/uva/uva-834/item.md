---
title: 'UVA-834 (Continued Fractions)'
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

vector<int> v;

void Exchange(int &a, int &b)
{
	int temp;
	temp = a;
	a = b;
	b = temp;
}

int main()
{
	int a,b, temp;
	int i;

	while(cin >> a >> b) {
		v.clear();
		if(a == 1) {
			printf("[0;%d]\n", b);
			continue;
		}
		else if(a<b) {
			Exchange(a, b);
			v.push_back(0);
		}
		while(b!=1) {
			v.push_back(a/b);
			temp = a;
			a=b;
			b = temp%b;
		}
		v.push_back(a);

		cout << "[" << v[0] << ";";
		for(i=1; i<v.size()-1; i++)
			cout << v[i] << ',';
		cout << v[i] << "]\n";
	}

return 0;
}
```