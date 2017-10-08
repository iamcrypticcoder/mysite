---
title: 'UVA-10496 (Collecting Beepers)'
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
    Time :
    Rank :
*/

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
#define NEG_BITS(mask) (mask ^ ALL_BITS)
#define TEST_BIT(mask, i) (mask & (1 << i))
#define ON_BIT(mask, i) (mask | (1 << i))
#define OFF_BIT(mask, i) (mask & NEG_BITS(1 << i))

typedef long long LL;
typedef unsigned long long ULL;
typedef vector<int> VI;
typedef vector<vector<int> > VVI;
typedef vector<string> VS;
typedef vector<bool> VB;
typedef vector< vector<bool> > VVB;
typedef pair<int, int> PII;
typedef map<int, int> MII;
typedef map<char, int> MCI;
typedef map<string, int> MSI;

int GCD(int a,int b){   while(b)b^=a^=b^=a%=b;  return a;   }

#define WHITE 0
#define GRAY 1
#define BLACK 2

#define MAX_NODES 11

int NODES;
int dist[MAX_NODES][MAX_NODES];
int DP[MAX_NODES][ 1 << MAX_NODES ];
vector<PII> pnts;

int TSP(int pos, int mask)
{
    if(DP[pos][mask] != -1) return DP[pos][mask];

    if(mask == (1 << NODES)-1) return dist[pos][0];

    int ret = INF;
    FOR(i, 0, NODES-1)
        if(i != pos && TEST_BIT(mask, i) == 0)
            ret = min(ret, dist[pos][i] + TSP(i, mask | (1 << i)));

    return DP[pos][mask] = ret;
}


int main()
{
    READ("input.txt");
//    WRITE("output.txt");

    int TC, tc;
    int a, b;

    scanf("%d", &TC);

    FOR(tc, 1, TC) {
        scanf("%d %d", &a, &b);
        scanf("%d %d", &a, &b);

        pnts.PB(PII(a, b));

        scanf("%d", &NODES);
        FOR(i, 1, NODES) {
            scanf("%d %d", &a, &b);
            pnts.PB(PII(a, b));
        }
        NODES = NODES + 1;      // Because of starting node

        FOR(i, 0, pnts.SZ-1) FOR(j, 0, pnts.SZ-1)
            dist[i][j] = abs(pnts[i].first - pnts[j].first) + abs(pnts[i].second - pnts[j].second);

        memset(DP, -1, sizeof DP);
        printf("The shortest path has length %d\n", TSP(0, 1));

        pnts.clear();
    }

    return 0;
}
```