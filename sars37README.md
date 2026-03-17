Problem Statement:

You have n coins and you want to build a staircase with these coins. The staircase consists of k rows where the ith row has exactly i coins. The last row of the staircase may be incomplete.

Given the integer n, return the number of complete rows of the staircase you will build.

CODE:

class Solution {
    public int arrangeCoins(int n) {

        long x=-1;
        long l=1,h=n;
        while(l<=h){
            long m=l+(h-l)/2;
            if(m*(m+1)/2==(long)n) return (int)m;
            else if(m*(m+1)/2<(long)n){
                x=m;
                l=m+1;
            }
            else h=m-1;
        }
        return (int)x;
        
    }
}
