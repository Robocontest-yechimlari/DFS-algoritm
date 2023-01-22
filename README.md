# DFS-algoritm
Dfs graph sorting algorithm
// dfs algoritmi C++
// yo'naltirilmagan graflar uchun
#include <bits/stdc++.h>
using namespace std;
vector<int> adj[1000];
bool vis[1000];
void dfs(int u)
{
    vis[u]=true;
    cout << u << " ";
    for(auto x : adj[u])
    {
        if(vis[x]==false)
        {
           dfs(x);
        }
    }
}
//  kiritilayotgan 2ta tugunni bir biri bilan bog'lash
void add( int u, int v)
{
    adj[u].push_back(v);
    adj[v].push_back(u);
}
int main()
{
    int n ,m , u ,v ;
     cin >> n >> m;
     // n tugunlar soni m ular orasidagi qirralar soni ularni bog'langanlarini kiritish
     for(int i=0; i<m; i++)
     {
         cin >> u >> v;
         add(u,v);
     }
     for(int i=0; i<n; i++)
     {
         cout << i << " ";
         for(auto x: adj[i])
         {
             cout << x << " ";
         }
          cout << endl;
     }
     
     dfs(0);
     return 0;
}
