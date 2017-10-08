---
title: 'UVA-10200 (Prime Time)'
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
#include <math.h>
#include <stdio.h>

#define EPS 1e-11

using namespace std;

unsigned long prime[4000];
unsigned long total_prime=2;

int Is_prime(unsigned long num)
{
	unsigned long root = sqrt((double)num);
	for(int i=0; prime[i] <= root; i++)
		if(!(num % prime[i]))
			return 0;
	return 1;
}

void PRIME_NUM_GENERATOR()
{
	unsigned long num;
	int Is_p, i;
	unsigned long ele = 2;

	prime[0] = 2;
	prime[1] = 3;

	for(num = 4; num <=20000; num++) {
		Is_p = 1;
		for(i =0; prime[i] <= sqrt((double)num); i++)
			if(!(num % prime[i])) {
				Is_p = 0;
				break;
			}
		if(Is_p) {
			prime[ele++] = num;
			total_prime++;
		}
	}
}

char rem[10001];

int main()
{
	unsigned long a, b, i;
	double actual_prime, gen_prime;

	PRIME_NUM_GENERATOR();

	while(scanf("%ld %ld", &a, &b) == 2) {
		actual_prime = gen_prime = 0;

		for(i=a; i<=b; i++) {
			if(rem[i] == 1)
				actual_prime++;
			else if(rem[i] == 2) continue;

			else {
				if(Is_prime(i*i+i+41))	{	actual_prime++;	rem[i] = 1;	}
				else rem[i] = 2;
			}
		}
				printf("%.2lf\n", ((actual_prime/(b-a+1)) * 100)+EPS);
	}

return 0;
}
```