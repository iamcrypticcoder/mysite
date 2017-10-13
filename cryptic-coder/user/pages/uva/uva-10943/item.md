---
title: 'UVA-10943 (How do you add)'
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
#include <set>
#include <map>
#include <list>
#include <cmath>
#include <ctime>
#include <queue>
#include <stack>
#include <cctype>
#include <cstdio>
#include <string>
#include <vector>
#include <cassert>
#include <cstdlib>
#include <cstring>
#include <sstream>
#include <iostream>
#include <algorithm>

using namespace std;

#define FOR(i, L, U) for(int i=(int)L; i<=(int)U; i++)
#define FORD(i, U, L) for(int i=(int)U; i>=(int)L; i--)

#define READ(x) freopen(x, "r", stdin)
#define WRITE(x) freopen(x, "w", stdout)

#define PQ priority_queue
#define PB push_back
#define SZ size()

#define SQR(x) ((x)*(x))
#define INF 99999999

#define ALL_BITS ((1 << 31) - 1)
#define NEG_BITS(mask) (mask ^= ALL_BITS)
#define TEST_BIT(mask, i) (mask & (1 << i))
#define ON_BIT(mask, i) (mask |= (1 << i))
#define OFF_BIT(mask, i) (mask &= NEG_BITS(1 << i))

typedef long long LL;
typedef unsigned long long ULL;
typedef vector<int> VI;
typedef vector<vector<int> > VVI;
typedef vector<string> VS;
typedef vector<bool> VB;
typedef vector< vector<bool> > VVB;
typedef pair<int, int> II;
typedef map<int, int> MII;
typedef map<char, int> MCI;
typedef map<string, int> MSI;

int GCD(int a,int b){   while(b)b^=a^=b^=a%=b;  return a;   }

#define WHITE 0
#define GRAY 1
#define BLACK 2

#define MOD 1000000

int N, K;
int DP[101][101];

int ways(int N, int K)
{
    if(DP[N][K] != -1) return DP[N][K];
    if(N == 0 || K == 1) return DP[N][K] = 1;

    int ret = 0;
    FOR(i, 0, N)
        ret = (ret + ways(N - i, K - 1)) % MOD;
    return DP[N][K] = ret;
}
int main()
{
//    READ("input.txt");
//    WRITE("output.txt");

    int TC, tc;

    memset(DP, -1, sizeof DP);

    while(cin >> N >> K) {
        if( N == 0 && K == 0 ) break;
        printf("%d\n", ways(N, K));
    }
    return 0;
}
```