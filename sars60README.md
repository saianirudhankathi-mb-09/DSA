Problem Statement:

Given two strings str1 and str2, find the length of their longest common substring.



A substring is a contiguous sequence of characters within a string.

CODE:

class Solution {
    public int longestCommonSubstr(String str1, String str2) {
        int dp[][]=new int[str1.length()+1][str2.length()+1];
        return ask(str1.str2,1,1,dp,0);
    }
    int ask(String s1,String s2,int i, int j,int dp[][],int max){
        if(i>s1.length()  ||  j>s2.length()) return 0;
        if(s1.charAt(i-1)==s2.charAt(j-1)){
            dp[i][j]=1+ask(s1,s2,i+1,j+1,dp,max);
        }
        else{
            dp[i][j]=Math.max(ask(s1,s2,i+1,j,dp,max),ask(s1,s2,i,j+1,dp,max));
        }
        max=Math.max(max,dp[i][j]);
        return max;
    }
}
