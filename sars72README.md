Problem Statement:

You are given an m x n integer array grid. There is a robot initially located at the top-left corner (i.e., grid[0][0]). The robot tries to move to the bottom-right corner (i.e., grid[m - 1][n - 1]). The robot can only move either down or right at any point in time.

An obstacle and space are marked as 1 or 0 respectively in grid. A path that the robot takes cannot include any square that is an obstacle.

Return the number of possible unique paths that the robot can take to reach the bottom-right corner.

The testcases are generated so that the answer will be less than or equal to 2 * 109.

CODE:

class Solution {
    public int uniquePathsWithObstacles(int[][] m) {
        for(int i=0;i<m.length;i++){
            for(int j=0;j<m[0].length;j++){
                if(m[i][j]==1) m[i][j]=-1;
            }
        }
        for(int i=0;i<m.length;i++){
            if(m[i][0]==-1) break;
            m[i][0]=1;
        }
        for(int i=0;i<m[0].length;i++){
            if(m[0][i]==-1) break;
            m[0][i]=1;
        }
        for(int i=1;i<m.length;i++){
            for(int j=1;j<m[0].length;j++){
                if(m[i][j]!=-1){
                    m[i][j]=((m[i-1][j]!=-1)?m[i-1][j]:0)+((m[i][j-1]!=-1)?m[i][j-1]:0);
                }
            }
        }
        return (m[m.length-1][m[0].length-1]==-1)?0:m[m.length-1][m[0].length-1];
    }
}
