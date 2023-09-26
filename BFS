#include<bits/stdc++.h>
using namespace std;
vector<vector<int> >vec(1001);
void bfs(bool visited[], int size,int start_node)
{
    queue<int> q;
    q.push(start_node);
    visited[start_node] = true;
    while (!q.empty())
    {
        int i = q.front();
        q.pop();
        for (int j = 0; j < vec[i].size(); j++)
        {
            if (!visited[vec[i][j]])
            {
                q.push(vec[i][j]);
                visited[vec[i][j]]=true;
            }
        }
        cout << i << " ";
    }
}

int main()
{
    int e, v;
    cout << "Enter the number of edges: ";
    cin >> e;
    cout << "Enter the number of vertices: ";
    cin >> v;
  
    int x, y;
    for (int i = 0; i < e; i++)
    {
        cout << "Enter the starting and ending vertex of edge " << (i + 1) << ": ";
        cin >> x >> y;
        vec[x].push_back(y);
        vec[y].push_back(x);
    }
    cout << "The  list representation of the graph is:\n";
    for(int i = 0; i < v; i++)
    {
        cout << i << ": ";
        for(int j = 0; j < vec[i].size(); j++)
        {
            cout << vec[i][j] << " ";
        }
        cout << endl;
    }
    bool visited[v + 1];
    memset(visited, false, sizeof(visited));
    cout<<"BFS Traversal: ";
    int n;
    cin>>n;
    bfs(visited, v,n);
    return 0;
}
