QUESTION'S LINK:-> https://www.codechef.com/problems/HOTMEALS?tab=statement
#include <bits/stdc++.h>
using namespace std;

#define ull unsigned long long
#define pb push_back
#define ld long double
#define ll long long

mt19937 rnd(51);
const ll INF = 1e18;
const int N = 5e5 + 10;

int input[N];
int n;
ll additional[N * 4];

struct Node {
    int count;
    ll maximum;
} tree[N * 4];

void increase(int v, ll value) {
    tree[v].maximum += value;
    additional[v] += value;
}

void propagate(int v) {
    increase(v * 2, additional[v]);
    increase(v * 2 + 1, additional[v]);
    additional[v] = 0;
}

int findSolution(int v, int left, int right, ll value) {
    if (left == right) {
        return (tree[v].maximum > value);
    }
    propagate(v);
    int middle = (left + right) / 2;
    if (tree[v * 2 + 1].maximum <= value) {
        return findSolution(2 * v, left, middle, value);
    } else {
        return findSolution(2 * v + 1, middle + 1, right, value) + tree[v].count - tree[v * 2 + 1].count;
    }
}

void updateTree(int v, int left, int right) {
    int middle = (left + right) / 2;
    tree[v].count = tree[v * 2 + 1].count + findSolution(v * 2, left, middle, tree[v * 2 + 1].maximum);
    tree[v].maximum = max(tree[v * 2].maximum, tree[v * 2 + 1].maximum);
}

void buildTree(int v, int left, int right) {
    if (left == right) {
        tree[v] = {1, input[left]};
        return;
    }
    int middle = (left + right) / 2;
    buildTree(2 * v, left, middle);
    buildTree(2 * v + 1, middle + 1, right);
    updateTree(v, left, right);
}

void modifyTree(int v, int treeLeft, int treeRight, int left, int right, int value) {
    if (left > right) return;
    if (treeLeft == left && treeRight == right) {
        increase(v, value);
        return;
    }
    propagate(v);
    int middle = (treeLeft + treeRight) / 2;
    modifyTree(2 * v, treeLeft, middle, left, min(right, middle), value);
    modifyTree(2 * v + 1, middle + 1, treeRight, max(left, middle + 1), right, value);
    updateTree(v, treeLeft, treeRight);
}

pair<int, ll> queryTree(int v, int treeLeft, int treeRight, int left, int right, ll maximum) {
    if (left > right) return {0, -INF};
    if (treeLeft == left && treeRight == right) {
        int result = findSolution(v, left, right, maximum);
        return {result, max(tree[v].maximum, maximum)};
    }
    propagate(v);
    int middle = (treeLeft + treeRight) / 2;
    pair<int, ll> rightResult = queryTree(2 * v + 1, middle + 1, treeRight, max(left, middle + 1), right, maximum);
    maximum = max(maximum, rightResult.second);
    pair<int, ll> leftResult = queryTree(2 * v, treeLeft, middle, left, min(right, middle), maximum);
    return {leftResult.first + rightResult.first, max(maximum, leftResult.second)};
}

int main() {
    #ifdef LOCAL
        freopen("input.txt", "r", stdin);
    #endif // LOCAL

    ios_base::sync_with_stdio(0);
    cin.tie(0);

    cin >> n;
    for (int i = 0; i < n; i++) {
        cin >> input[i];
        input[i] -= i;
    }

    buildTree(1, 0, n - 1);
    cout << n - tree[1].count << endl;

    int q;
    cin >> q;
    while (q--) {
        int type, left, right;
        cin >> type >> left >> right;
        left--, right--;
        if (type == 1) {
            cout << (right - left + 1) - queryTree(1, 0, n - 1, left, right, -INF).first << endl;
        } else {
            int weight;
            cin >> weight;
            modifyTree(1, 0, n - 1, left, right, weight);
        }
    }

    return 0;
}
