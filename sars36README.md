Problem Statement:

Given two numbers N and M, find the Nth root of M. The Nth root of a number M is defined as a number X such that when X is raised to the power of N, it equals M. If the Nth root is not an integer, return -1.

CODE:

class Solution {
    public int NthRoot(int N, int M) {
        int l=1,h=M;
        while(l<=h){
            int mid=l+(h-l)/2;
            long x=ask(mid,N,M);
            if(x==(long)M) return mid;
            else if(x>(long)M) h=mid-1;
            else l=mid+1;
        }
        return -1;
    }
    long ask(int mid,int n,int m){
        long x=1;
        while(n--!=0  &&  x<=m){
            x*=mid;
        }
        return x;
    }
}
