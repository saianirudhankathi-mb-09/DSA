Problem Statement:

Given a undirected Graph consisting of V vertices numbered from 0 to V-1 and E edges. The ith edge is represented by [ai,bi], denoting a edge between vertex ai and bi. We say two vertices u and v belong to a same component if there is a path from u to v or v to u. Find the number of connected components in the graph.



A connected component is a subgraph of a graph in which there exists a path between any two vertices, and no vertex of the subgraph shares an edge with a vertex outside of the subgraph.+

CODE:

class Solution {
    public int findNumberOfComponent(int V, List<List<Integer>> edges) {
        int sl[]=new int[V];
        for(int i=0;i<V;i++){
            sl[i]=i;
        }
        int sz=V;
        for(List<Integer> l:edges){
            int x=ask(l.get(0),sl),y=ask(l.get(1),sl);
            if(x!=y){
                sl[y]=x;
                sz--;
            }
        }
        return sz;
    }
    int ask(int a,int sl[]){
        if(sl[a]==a) return a;
        return sl[a]=ask(sl[a],sl);
    }
}
