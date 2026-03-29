Problem Statement:

Given a positive integer n. Find and return its square root. If n is not a perfect square, then return the floor value of sqrt(n).

CODE:

class Solution {
    public int floorSqrt(int n) {

        int l=1,h=n,x=-1;

        while(l<=h){
            int mid=l+(h-l)/2;
            if(mid*mid==n) return mid;
            else if(mid*mid<n){
                x=mid;
                l=mid+1;
            }
            else{
                h=mid-1;
            }
        }
        return x;
      
    }
}
