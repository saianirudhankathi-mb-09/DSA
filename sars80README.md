Problem Statement:

Implement pow(x, n), which calculates x raised to the power n (i.e., xn).

CODE:

class Solution {
    public double myPow(double x, int n) {
        boolean b=false;
        long p=n;
        if(p<0){
            b=true;
            p*=-1;
        }
        double ans=ask(x,p);
        if(b) return 1/(ans);
        return (ans);
    }
    double ask(double x,long n){
        if(n==0) return 1;
        if(n==1) return x;
        double ans=ask(x,n/2);
        if((n&1)!=0){ 
            return ans*ans*x;
        }
        return ans*ans;
    }
}
