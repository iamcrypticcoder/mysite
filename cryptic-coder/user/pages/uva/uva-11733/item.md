---
title: 'UVA-11733 (Airports)'
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
#define ff first
#define ss second

#define EPS 1e-9
#define SQR(x) ((x)*(x))
#define INF 99999999

#define ALL_BITS ((1 << 31) - 1)
#define NEG_BITS(mask) (mask ^= ALL_BITS)
#define TEST_BIT(mask, i) (mask & (1 << i))
#define ON_BIT(mask, i) (mask |= (1 << i))
#define OFF_BIT(mask, i) (mask &= NEG_BITS(1 << i))

typedef long long LL;
typedef vector<char> VC;
typedef vector<vector<char> > VVC;
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

int dx[] = {1, -1, 0, 0};
int dy[] = {0, 0, -1, 1};

inline int src() { int ret; scanf("%d", &ret); return ret; }

// ------------------------- GLOBAL VARIABLES --------------------------------
int airportCost;

//---------------------------- KRUSKAL ALGO START --------------------------
typedef struct {
    int u, v;
    int w;
} EDGE;

int NODES, EDGES;
vector<EDGE> edges;
vector<EDGE> spanEdge;
int minSpanCost;

// -------------------- Disjoint Set Structure --------------------------------------
int set[10001];
void InitSet(int N)     {   FOR(i, 1, N)    set[i] = i;     }
int FindSet(int u)      {   return set[u] == u ? u : (set[u] = FindSet(set[u]));    }
void Union(int u, int v){   set[FindSet(u)] = FindSet(v); }
// ----------------------------------------------------------------------------------

bool compEdge(EDGE a, EDGE b)
{
    return a.w < b.w;
}

void Kruscal()
{
	int p, q;

	minSpanCost = 0;

	for(int i=0; i < EDGES; i++) {
		p = FindSet(edges[i].u);
		q = FindSet(edges[i].v);
		if(p != q && edges[i].w < airportCost) {
			spanEdge.push_back(edges[i]);
			Union(p, q);
			minSpanCost += edges[i].w;
			if(spanEdge.size() == NODES - 1) break;
		}
	}
}
//---------------------------- KRUSKAL ALGO END --------------------------

int main()
{
    READ("input.txt");
    WRITE("output.txt");
   int i, j, k;
   int TC, tc;
   EDGE e;

   TC = src();

   FOR(tc, 1 ,TC) {
      NODES = src();
      EDGES = src();
      airportCost = src();

      FOR(i, 1, EDGES) {
         scanf("%d %d %d", &e.u, &e.v, &e.w);
         edges.PB(e);
      }
      InitSet(NODES+1);
      sort(edges.begin(), edges.end(), compEdge);
      Kruscal();

      int numOfSets = 0;
      FOR(i, 1, NODES) {
         if(set[i] == i) numOfSets++;
      }

      printf("Case #%d: %d %d\n", tc, minSpanCost+numOfSets*airportCost, numOfSets);

      edges.clear();
      spanEdge.clear();
   }

   return 0;
}
```