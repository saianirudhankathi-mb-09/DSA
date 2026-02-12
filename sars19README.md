Problem Statement:

You are a professional robber planning to rob houses along a street. Each house has a certain amount of money stashed. All houses at this place are arranged in a circle. That means the first house is the neighbor of the last one. Meanwhile, adjacent houses have a security system connected, and it will automatically contact the police if two adjacent houses were broken into on the same night.

Given an integer array nums representing the amount of money of each house, return the maximum amount of money you can rob tonight without alerting the police.

CODE:

class Solution {
    public int rob(int[] nums) {
        
        if(nums.length==1) return nums[0];

        int dp1[]=new int[nums.length];
        int dp2[]=new int[nums.length];

        Arrays.fill(dp1,-1);
        Arrays.fill(dp2,-1);


        int x=ask(nums,dp1,0,nums.length-1);
        int y=ask(nums,dp2,1,nums.length);

        return Math.max(x,y);


    }

    int ask(int a[],int dp[],int i,int n){
        if(i>=n) return 0;

        if(dp[i]!=-1) return dp[i];

        return dp[i]=Math.max(a[i]+ask(a,dp,i+2,n),ask(a,dp,i+1,n));
    }

}
