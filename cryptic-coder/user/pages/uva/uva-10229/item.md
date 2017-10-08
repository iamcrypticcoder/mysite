---
title: 'UVA-10229 (Modular Fibonacci)'
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

int GCD(int a,int b) {   while(b)b^=a^=b^=a%=b;  return a;   }
int LCM(int a,int b) {   return a / GCD(a, b) * b;   }

#define WHITE 0
#define GRAY 1
#define BLACK 2

int dx[] = {1, -1, 0, 0};
int dy[] = {0, 0, -1, 1};

inline int src() { int ret; scanf("%d", &ret); return ret; }

//---------------------------- GLOBAL VARIABLES ----------------------------


#define MAX_N 105

struct Matrix {
   LL mat[MAX_N][MAX_N];
};

int n, m, MOD;
int matOrder;
Matrix matA, matB;

Matrix matMul(Matrix a, Matrix b)
{
   Matrix ans;
   int i, j, k;
   FOR(i, 0, matOrder-1)
      FOR(j, 0, matOrder-1) {
         ans.mat[i][j] = 0;
         FOR(k, 0, matOrder-1) {
            ans.mat[i][j] = (ans.mat[i][j] += (a.mat[i][k] * b.mat[k][j]) % MOD) % MOD;
            //ans.mat[i][j] %= (1 << m);
         }
      }
   return ans;
}

// Using this function you will get Time: 0.216
Matrix matPow(Matrix base, int p)
{
   Matrix ans;
   int i, j;

   FOR(i, 0, matOrder-1) FOR(j, 0, matOrder-1) ans.mat[i][j] = (i == j);

   int count = 1;
   while(p) {
      //cout << count++ <<  endl;
      if(p & 1) ans = matMul(ans, base);
      base = matMul(base, base);
      p >>= 1;
   }
   return ans;
}

void showMat(Matrix m)
{
   FOR(i, 0, matOrder-1) {
      FOR(j, 0, matOrder-1) cout << m.mat[i][j] << " ";
      cout << endl;
   }
}

// Using this function you will get Time: 0.008
long long Fib(long long N)
{
   LL i = 1, j = 0, k = 0, h = 1;
   LL t;

   while(N > 0) {
      if(N & 1) {
         t = (j * h) % MOD;
         j = ((i*h)%MOD + (j*k)%MOD + t%MOD) % MOD;
         i = (i*k + t) % MOD;
      }
      t = SQR(h) % MOD;
      h = (2*k*h + t) % MOD;
      k = (SQR(k) + t) % MOD;
      N = N/2;
   }
   return j;
}

int main()
{
//    READ("input.txt");
//    WRITE("output.txt");
   int i, j, k;
   int TC, tc;

   //cout << Fib(5);
   // | 1 1 |
   // | 1 0 |
   matOrder = 2;
   matA.mat[0][0] = 1; matA.mat[0][1] = 1;
   matA.mat[1][0] = 1; matA.mat[1][1] = 0;


   while(scanf("%d %d", &n , &m) != EOF) {
      MOD = (1 << m);
      matB = matPow(matA, n);

      //showMat(matB);

      printf("%lld\n", matB.mat[0][1]);

      printf("%lld\n", Fib(n));
   }

   return 0;
}
```