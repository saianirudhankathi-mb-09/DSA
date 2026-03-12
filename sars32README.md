Problem Statement:

Given a m x n grid filled with non-negative numbers, find a path from top left to bottom right, which minimizes the sum of all numbers along its path.

Note: You can only move either down or right at any point in time.

CODE:

class Solution {
    public int minPathSum(int[][] m) {
        for(int i=1;i<m[0].length;i++){
            m[0][i]+=m[0][i-1];
        }
        for(int i=1;i<m.length;i++){
            m[i][0]+=m[i-1][0];
        }
        for(int i=1;i<m.length;i++){
            for(int j=1;j<m[0].length;j++){
                m[i][j]+=Math.min(m[i-1][j],m[i][j-1]);
            }
        }
        return m[m.length-1][m[0].length-1];
    }
}
