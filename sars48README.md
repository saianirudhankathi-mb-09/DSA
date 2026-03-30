Problem Statement:

You are given an integer n. You need to check whether it is an armstrong number or not. Return true if it is an armstrong number, otherwise return false.



An armstrong number is a number which is equal to the sum of the digits of the number, raised to the power of the number of digits.

CODE:

class Solution {
    public boolean isArmstrong(int n) {

        StringBuilder sb=new StringBuilder(n+"");
        int l=sb.length();
        int sum=0;
        for(char ch:sb.toString().toCharArray()){
            sum+=Math.pow(ch-'0',l);
        }

        // System.out.println(sum);

        return (sum==n);

    }
}
