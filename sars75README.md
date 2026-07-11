Problem Statement:

You are climbing a staircase. It takes n steps to reach the top.

Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?

CODE:

class Solution {
    public int climbStairs(int n) {
        if(n==1) return 1;
        // if(n==2) return 2;
        int curr=1,prev=1;
        for(int i=2;i<=n;i++){
            int x=prev+curr;
            prev=curr;
            curr=x;
        }
        return curr;
    }
}
