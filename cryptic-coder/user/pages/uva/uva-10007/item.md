---
title: 'UVA-10007 (Count the Trees)'
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
/*
    Time :		0.505
    Rank :		957
    Complexity:
*/

import java.math.BigInteger;
import java.util.Scanner;


public class Main {
	
	public static BigInteger[] cats = new BigInteger[301];
	public static BigInteger[] facts = new BigInteger[301];
	
	public static void generateFactorials() {
		facts[0] = BigInteger.ONE;
		for(int i = 1; i <= 300; i++) {
			facts[i] = facts[i-1].multiply(BigInteger.valueOf(i));
		}
	}
	public static void generateCatalans() {
		cats[0] = BigInteger.ONE;
		for(int i = 1; i <= 300; i++) {
			int n = i-1;
			cats[i] = BigInteger.valueOf(2 * (2*n + 1));
			cats[i] = cats[i].multiply(cats[n]);
			cats[i] = cats[i].divide(BigInteger.valueOf(n+2));
		}
	}
	
	public static void main(String args[]) {
		Scanner scr = new Scanner(System.in);
		
		generateFactorials();
		generateCatalans();
		
		while(scr.hasNextInt()) {
			int n = scr.nextInt();
			if(n == 0) break;
			BigInteger temp = cats[n].multiply(facts[n]);
			System.out.println(temp.toString());
		}
	}
}
```