Problem Statement:

Given an array arr of n integers and an integer K, count the number of subsets of the given array that have a sum equal to K. Return the result modulo (109 + 7).

CODE:

class Solution {
    public int perfectSum(int[] arr, int k) {
        int ct=0,m=1000000007;
        int dp[][]=new int[arr.length+1][k+1];
        for(int i=0;i<arr.length+1;i++){
            dp[i][0]=1;
        }
        for(int i=1;i<arr.length+1;i++){
            for(int j=1;j<k+1;j++){
                // boolean t=false,nt=false;
                // nt=dp[i-1][k];
                    // t=dp[i-1][j-arr[i-1]];
                // dp[i][j]=t||nt;
                // if(dp[i][j]) ct++;
                if(j-arr[i-1]>=0){
                    dp[i][j]=dp[i-1][j-arr[i-1]]%m;
                }
                dp[i][j]=(dp[i][j]%m+dp[i-1][j]%m)%m;
            }
        }
        // for(int i=0;i<arr.length+1;i++){
        //     if(dp[i][k]) ct++;
        // }
        return dp[arr.length][k]%m;
    }
}

