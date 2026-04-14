Problem Statement:

Given a string s. In one step you can insert any character at any index of the string.

Return the minimum number of steps to make s palindrome.

A Palindrome String is one that reads the same backward as well as forward.

CODE:

class Solution {
    public int minInsertions(String s) {
        int dp[][]=new int[s.length()][s.length()];
        // int min=0;
        for(int a[]:dp) Arrays.fill(a,-1);
        return ask(s,0,s.length()-1,dp);
    }
    int ask(String str,int i,int j,int dp[][]){
        if(i>=j) return 0;

        if(dp[i][j]!=-1) return dp[i][j];

        if(str.charAt(i)==str.charAt(j)){
            // dp[i][j]=0;
            return dp[i][j]=ask(str,i+1,j-1,dp);
        }
        return dp[i][j]=1+Math.min(ask(str,i+1,j,dp),ask(str,i,j-1,dp));
        // min=Math.max(min,dp[i][j]);
        // return min;
    }
}
