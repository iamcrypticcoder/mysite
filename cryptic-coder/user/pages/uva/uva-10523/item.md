---
title: 'UVA-10523 (VERY EASY)'
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

```java
import java.util.Scanner;
import java.math.BigInteger;

class Main {
	
	public static void main(String args[])
	{
		
		Scanner scr = new Scanner(System.in);
		
		while(scr.hasNext()) {
			
			int N = scr.nextInt();
			int A = scr.nextInt();
			
			BigInteger ans = BigInteger.ZERO;
			
			for(int i=1; i<= N; i++) {
				ans = ans.add(BigInteger.valueOf(i).multiply(BigInteger.valueOf(A).pow(i)));
			}

                        System.out.println(ans);
		}
	}
}
```