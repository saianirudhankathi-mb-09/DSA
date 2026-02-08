Problem Statement:

Given three numbers A, B M. The task is to find (AB)%M.

CODE:

class BeingZero {
    public long solve(long A, long B, long M) {
        long ans = 1;
        //complete the function
        
        return ask(A,B,M);
    }

    long ask(long a,long b,long m){
        if(b==1){
            return a;
        }

        long ans=ask(a,b/2,m);

        ans=(ans%m*ans%m)%m;

        if((b&1)!=0){
            ans=(ans%m*a%m)%m;
        }

        return ans;
        
    }
}
