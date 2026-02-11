Problem Statement:

You are climbing a staircase. It takes n steps to reach the top.

Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?

CODE:

class Solution {

    int dp[]=new int[46];
    // Arrays.fill(dp,-1);
    public Solution(){
        
        dp[0]=1;
        dp[1]=1;
        dp[2]=2;

        for(int i=3;i<46;i++){
            dp[i]=dp[i-1]+dp[i-2];
        }

    }

    public int climbStairs(int n) {

        // if(dp[n]!=-1){
        //     return dp[n];
        // }

        // // return dp[n]=climbStairs(n-1)+climbStairs(n-2);
        // return dp[n]=((dp[n-1])!=-1?dp[n-1]:climbStairs(n-1))+((dp[n-2])!=-1?dp[n-2]:climbStairs(n-2));

        return dp[n];
    }
}
