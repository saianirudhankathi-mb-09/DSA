Problem Statement:

Given a 2D integer array A of size M x N, you need to find a path from top left to bottom right which minimizes the sum of all numbers along its path.

NOTE: You can only move either down or right at any point in time. 

CODE:

public class Solution {
    public int minPathSum(ArrayList<ArrayList<Integer>> A) {
        
        int dp[][]=new int[A.size()][A.get(0).size()];
        
        dp[0][0]=A.get(0).get(0);
        
        for(int j=1;j<A.get(0).size();j++){
            dp[0][j]=dp[0][j-1]+A.get(0).get(j);
        }
        
        for(int i=1;i<A.size();i++){
            dp[i][0]=dp[i-1][0]+A.get(i).get(0);
        }
        
        for(int i=1;i<A.size();i++){
            
            for(int j=1;j<A.get(0).size();j++){
                
                dp[i][j]=Math.min(dp[i-1][j],dp[i][j-1])+A.get(i).get(j);
                
            }
            
        }
        
        return dp[A.size()-1][A.get(0).size()-1];
        
    }
}

