Problem Statement:

You are given an m x n grid where each cell can have one of three values:

0 representing an empty cell,
1 representing a fresh orange, or
2 representing a rotten orange.
Every minute, any fresh orange that is 4-directionally adjacent to a rotten orange becomes rotten.

Return the minimum number of minutes that must elapse until no cell has a fresh orange. If this is impossible, return -1.

CODE:

class Solution {
    public int orangesRotting(int[][] grid) {
        int tl=grid.length*grid[0].length;
        Queue<Pair> q=new LinkedList<>();
        for(int i=0;i<grid.length;i++){
            for(int j=0;j<grid[0].length;j++){
                if(grid[i][j]==2){
                    q.add(new Pair(i,j,0));
                    tl--;
                }
                if(grid[i][j]==0) tl--;
            }
        }
        int max=0;
        while(!q.isEmpty()){
            Pair p=q.remove();
            int xi=p.i,yj=p.j,nct=p.ct;
            if(xi-1>=0  &&  grid[xi-1][yj]==1){
                q.add(new Pair(xi-1,yj,nct+1));
                grid[xi-1][yj]=2;
                max=Math.max(max,nct+1);
                tl--;
            }
            if(yj-1>=0  &&  grid[xi][yj-1]==1){
                q.add(new Pair(xi,yj-1,nct+1));
                grid[xi][yj-1]=2;
                max=Math.max(max,nct+1);
                tl--;
            }
            if(yj+1<grid[0].length  &&  grid[xi][yj+1]==1){
                q.add(new Pair(xi,yj+1,nct+1));
                grid[xi][yj+1]=2;
                max=Math.max(max,nct+1);
                tl--;
            }
            if(xi+1<grid.length  &&  grid[xi+1][yj]==1){
                q.add(new Pair(xi+1,yj,nct+1));
                grid[xi+1][yj]=2;
                max=Math.max(max,nct+1);
                tl--;
            }
        }
        if(tl==0) return max;
        return -1;
    }
}
class Pair{
    int i,j,ct;
    public Pair(int i,int j,int ct){
        this.i=i;
        this.j=j;
        this.ct=ct;
    }
}
