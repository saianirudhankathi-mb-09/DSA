Problem Statement:

Given an integer array nums, return true if you can partition the array into two subsets such that the sum of the elements in both subsets is equal or false otherwise.

CODE:

class Solution {
    public boolean canPartition(int[] nums) {
        int sum=0;
        for(int ele:nums) sum+=ele;

        if((sum&1)!=0) return false;

        Boolean dp[][]=new Boolean[nums.length][sum/2+1];


        return ask(dp,nums,sum/2,0);

    }

    boolean ask(Boolean dp[][],int a[],int t,int i){

        if(i>=a.length  ||  t<0) return false;

        if(t==0) return true;

        if(dp[i][t]!=null) return dp[i][t];


        return dp[i][t]=ask(dp,a,-a[i]+t,i+1)||ask(dp,a,t,i+1);

    }
}
        // Arrays.fill(dp,-1);

        // if(nums[0]==sum/2);

        // int x=ask(dp,nums,sum/2,0);

        // if(x==0) return true;
        // return false;
        // if(t==0) return dp[i]=0;

        // return dp[i]=Math.max(ask(dp,a,t-a[i],i+1),ask(dp,a,t,i+1)); 
