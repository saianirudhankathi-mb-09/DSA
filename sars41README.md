Problem Statement:

Given a signed 32-bit integer x, return x with its digits reversed. If reversing x causes the value to go outside the signed 32-bit integer range [-231, 231 - 1], then return 0.

Assume the environment does not allow you to store 64-bit integers (signed or unsigned).

CODE:

class Solution {
    public int reverse(int x) {
        boolean b=false;
        if(x<0) b=true;
        long y=Math.abs((long)x);
        // long y=(long)(x);
        // String str=y+"";
        StringBuilder sb=new StringBuilder(y+"");
        sb=sb.reverse();
        long z=Long.parseLong(sb.toString());
        if(z>(long)Integer.MAX_VALUE) return 0;
        return (b)?-1*(int)z:(int)z;
    }
}
