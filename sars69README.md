Problem Statement:

Given two strings str1 and str2, find the length of their longest common subsequence.



A subsequence is a sequence that appears in the same relative order but not necessarily contiguous and a common subsequence of two strings is a subsequence that is common to both strings.

CODE:

class Solution {
    public int lcs( String str1, String str2) {
        int dp[][]=new int[str1.length()+1][str2.length()+1];
        for(int i=1;i<str1.length()+1;i++){
            for(int j=1;j<str2.length()+1;j++){
                if(str1.charAt(i-1)==(str2.charAt(j-1))){
                    dp[i][j]=1;
                }
                dp[i][j]+=Math.max(dp[i-1][j],dp[i][j-1]);
            }
        }
        return dp[str1.length()][str2.length()];
    }
}

