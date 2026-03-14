Problem Statement:

Given a string s, find the longest palindromic subsequence's length in s.

A subsequence is a sequence that can be derived from another sequence by deleting some or no elements without changing the order of the remaining elements.

CODE:

class Solution {
    public int longestPalindromeSubseq(String s1) {
        StringBuilder sb=new StringBuilder(s1);
        String s2=sb.reverse().toString();
        int dp[][]=new int[s1.length()+1][s1.length()+1];
        for(int a[]:dp) Arrays.fill(a,-1);
        return ask(s1,s2,1,1,dp);
    }
    int ask(String s1,String s2,int i,int j,int dp[][]){
        if(i>s1.length()  ||  j>s2.length()) return 0;

        if(dp[i][j]!=-1) return dp[i][j];

        if(s1.charAt(i-1)==s2.charAt(j-1)){
            return dp[i][j]=1+ask(s1,s2,i+1,j+1,dp);
        }

        return dp[i][j]=Math.max(ask(s1,s2,i+1,j,dp),ask(s1,s2,i,j+1,dp));

    }
}
