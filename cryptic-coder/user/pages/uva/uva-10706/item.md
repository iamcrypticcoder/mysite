---
title: 'UVA-10706 (Number Sequence)'
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

#define EPS 1e-9
#define SQR(x) ((x)*(x))
#define INF 99999999
#define TO_DEG 57.29577951
#define PI 2*acos(0.0)

#define ALL_BITS ((1 << 31) - 1)
#define NEG_BITS(mask) (mask ^= ALL_BITS)
#define TEST_BIT(mask, i) (mask & (1 << i))
#define ON_BIT(mask, i) (mask |= (1 << i))
#define OFF_BIT(mask, i) (mask &= NEG_BITS(1 << i))

typedef long long LL;
typedef long long ULL;
typedef vector<int> VI;
typedef vector<vector<int> > VVI;
typedef vector<string> VS;
typedef vector<bool> VB;
typedef vector<char> VC;
typedef vector< vector<bool> > VVB;
typedef pair<int, int> PII;
typedef map<int, int> MII;
typedef map<char, int> MCI;
typedef map<string, int> MSI;

int GCD(int a,int b){   while(b)b^=a^=b^=a%=b;  return a;   }

// UP, RIGHT, DOWN, LEFT, UPPER-RIGHT, LOWER-RIGHT, LOWER-LEFT, UPPER-LEFT
int dx[8] = {-1, 0, 1, 0, -1, 1,  1, -1};
int dy[8] = { 0, 1, 0,-1,  1, 1, -1, -1};

// Represents all moves of a knight in a chessboard
int dxKnightMove[8] = {-1, -2, -2, -1,  1,  2, 2, 1};
int dyKnightMove[8] = { 2,  1, -1, -2, -2, -1, 1, 2};

inline int src() { int ret; scanf("%d", &ret); return ret; }

#define WHITE 0
#define GRAY 1
#define BLACK 2

#define MAX_LEN 1000001

vector<ULL> A;
string digits = "";

string intToString(int x) {
    string ret = "";
    while(x) {
        ret += (x % 10) + '0';
        x /= 10;
    }
    reverse(ret.begin(), ret.end());
    return ret;
}

int digitCount(int x) {
    if(x < 10)
        return 1;
    if(x < 100)
        return 2;
    if(x < 1000)
        return 3;
    if(x < 10000)
        return 4;
    if(x < 100000)
        return 5;
    if(x < 1000000)
        return 6;
    if(x < 10000000)
        return 7;
    if(x < 100000000)
        return 8;
}

void calcS()
{
    A.PB(0);
    A.PB(1);
    digits += "1";
    ULL lastSLen = 1;
    int k = 2;
    for(k=2; k <= 40000; k++) {
        lastSLen = lastSLen + digitCount(k);
        ULL sum = A[A.size()-1] + lastSLen;
        A.PB(sum);
        digits += intToString(k);
        //cout << digits << endl;
    }
}

int main()
{
    READ("input.txt");
    //WRITE("output.txt");
    int i, j, k;
    int TC, tc;
    double cl = clock();

    calcS();

    scanf("%d", &TC);
    FOR(tc, 1, TC) {
        ULL x = src();
        int low = lower_bound(A.begin(), A.end(), x) - A.begin();

        int remaining = x - A[low-1];
        cout << digits[remaining - 1] << endl;
    }

    cl = clock() - cl;
    fprintf(stderr, "Total Execution Time = %lf seconds\n", cl / CLOCKS_PER_SEC);

    return 0;
}
```