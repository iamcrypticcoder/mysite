---
title: 'UVA-146 (ID Codes)'
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
#include <string>
#include <algorithm>

using namespace std;

int main() {
   string s, temp;
	while(getline(cin,s)) {
		if(s == "#") break;
		temp = s;				
      next_permutation(temp.begin(), temp.end());
		reverse(s.begin(), s.end());
		if(s == temp) {
			cout << "No Successor\n";
			continue;
		}
      cout << temp << endl;
  }
}
```