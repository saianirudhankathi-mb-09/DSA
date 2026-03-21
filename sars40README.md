Problem Statement:

You are given an integer n. You need to return the number of digits in the number.



The number will have no leading zeroes, except when the number is 0 itself.

CODE:

class Solution {
    public int countDigit(int n) {
        // return (n+"").length();
        if(n==0) return 0;
        return (int)Math.log10(n)+1;
    }
}
