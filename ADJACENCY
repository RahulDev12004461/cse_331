#include<bits/stdc++.h>
using namespace std;

int main()
{
   
    //vector<vector<int > > vec(n);
   
    
    int e, v;
    cout << "Enter the number of edges: ";
    cin >> e;
    cout << "Enter the number of vertices: ";
    cin >> v;
     vector<int> vec[v];
    int x, y;
    for(int i=0;i<e; i++)
    {
        cout<< "Enter the starting and ending vertex of edge "<<(i+1)<< ": ";
        cin>>x>>y;
        vec[x].push_back(y);
        vec[y].push_back(x);
    }
    
    cout<< "The representation of the graph is"<<endl;
    for(int i = 0; i<v; i++)
    {
        cout <<i<<": ";
        for(int j= 0;j<vec[i].size(); j++)
        {
            cout<< vec[i][j] << " ";
        }
        cout << endl;
    }
    
    return 0;
}
