---
title: 'Classic DP Recurrence'
published: true
date: '00:05 11/02/2016'
taxonomy:
    category:
        - blog
    tag:
        - algorithm
        - dynamic-programming
body_classes: 'header-lite fullwidth blogstyling'
highlight:
    enabled: false
---

### Matrix Chain Multiplication (MCM)
```
Let, there are N matrices their dimension looks like: (p[0], p[1]), (p[1], p[2])... (p[N-1], p[N])

MCM(i, j) = 0                                                         if i == j
MCM(i, j) = min( MCM(i, k) + MCM(k+1, j) + p[i-1] * p[k] * p[j] )     if i < j
            i <= k < j

Desired Solution : MCM(1, N)
```
===


### Zero-one Knapsack
```
Let there are N items and array V contains value of items and W contains weight of items. 
MW is the knapsack size.

K(weight, i) = 0                                                      if i == 0 or w == 0
K(weight, i) = K(weight, index-1)                                     if weight < W[index]
K(weight, i) = max( K(weight, i-1), K(weight – W[i], i-1) + V[i] )    if weight >= W[index]

Desired Solution : K(MW, N)
```


### Coin Change (CC)
```
Let, there are N coins and array coins[] stores the value of coins.
How many ways we can make N taking those coins? We can use one coin unlimited times.

CC(N, i) = 1                                   if N == 0
CC(N, i) = 0                                   if N < 0
CC(N, i) = 0                                   if i > number of coins
CC(N, i) = CC(N – coins, i) + CC(N, i+1)

Desired Solution : CC(N, 0)
```


### Longest Increasing Subsequence (LIS)
```
Let, there are N integers and array A[] stores them. L[] contains LIS length.

LIS(i) = 1                            if i == 1
LIS(i) = max( LIS(j)+1, L[i])         for 1 <= j < i and A[j] < A[i]

Desired Solution : LIS(N)
```


### Travelling Salesman Problem (TSP)
```
Let, there are N cities and their all pair distance given in form matrix dist[][] assume we start from city 0

TSP(pos, bitmask) = dist[pos][0]                  if bitmask = 2^N – 1
TSP(pos, bitmask) = min(dist[pos][nxt] + TSP(nxt, bitmask | (1 << nxt)))
for 0 <= nxt <= N-1 and nxt != pos and (bitmask & (1 << nxt)) is 0

Desired Solution : TSP(0, 1 << 0)
```

