Problem Statement:

Given an integer x, return true if x is a palindrome, and false otherwise.

CODE:

class Solution {
    public boolean isPalindrome(int x) {
        String ans="";
        String a1=x+"";
        if(x==0)
        return true;
        while(x>0){
            ans+=x%10+"";
            x=x/10;
        }
        if(ans.equals(a1))
            return true;
        return false;
    }
}
