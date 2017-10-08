---
title: 'LIGHTOJ-1069 (Lift)'
published: true
date: '00:05 11/02/2016'
taxonomy:
    category:
        - blog
    tag:
        - light-oj
body_classes: 'header-lite fullwidth blogstyling'
---

Here is full code:

===

```cpp
#include <stdio.h>

int main()
{
    int tc, TC;
    int posMe, posLift;
    int ans;

    scanf("%d", &TC);

    for(tc = 1; tc <= TC; tc++) {
        scanf("%d %d", &posMe, &posLift);

        if(posLift > posMe) ans =(posLift - posMe) * 4 + posMe*4 + 19;
        else ans = (posMe - posLift) * 4 + posMe*4 + 19;

        printf("Case %d: %d\n", tc, ans);
    }

    return 0;
}
```