Problem Statement:

Given an undirected connected graph with V vertices numbered from 0 to V-1, the task is to implement both Depth First Search (DFS) and Breadth First Search (BFS) traversals starting from the 0th vertex.



The graph is represented using an array/vector of edges, where each element is a pair [u, v] indicating an undirected edge between vertex u and vertex v.

CODE:

class Solution {
    public List<Integer> dfsOfGraph(int V, List<List<Integer>> adj) {
        List<Integer> ans=new ArrayList<>();
        // Stack<Integer> st=new Stack<>();
        List<List<Integer>> al=new ArrayList<>();
        for(int i=0;i<V;i++){
            al.add(new ArrayList<>());
        }
        for(List<Integer> l:adj){
            al.get(l.get(0)).add(l.get(1));
            al.get(l.get(1)).add(l.get(0));
        }
        boolean vis[]=new boolean[V];
        dfs(0,al,ans,vis);
        return ans;
    }
    
    public List<Integer> bfsOfGraph(int V, List<List<Integer>> adj) {
        List<Integer> ans=new ArrayList<>();
        Queue<Integer> q=new LinkedList<>();
        List<List<Integer>> al=new ArrayList<>();
        for(int i=0;i<V;i++){
            al.add(new ArrayList<>());
        }
        for(List<Integer> l:adj){
            al.get(l.get(0)).add(l.get(1));
            al.get(l.get(1)).add(l.get(0));
        }
        boolean vis[]=new boolean[V];
        q.add(0);
        vis[0]=true;
        while(!q.isEmpty()){
            int x=q.remove();
            ans.add(x);
            // for(List<Integer> l:al){
                // if(l.get(0)==x  &&  !vis[l.get(1)]){
                //     vis[l.get(1)]=true;
                //     q.add(l.get(1));
                // }
                for(int z:al.get(x)){
                    if(!vis[z]){
                        q.add(z);
                        vis[z]=true;
                    }
                }
            // }
        }
        return ans;
    }
    public void dfs(int ele,List<List<Integer>> al,List<Integer> ans,boolean vis[]){
        if(vis[ele]) return;
        vis[ele]=true;
        ans.add(ele);
        for(int x:al.get(ele)){
            // for(int x:l)
            dfs(x,al,ans,vis);
        }
        return;
    }
}

