Problem Statement:

Given three numbers A, B M. The task is to find (AB)%M.

CODE:

class BeingZero {
    public long solve(long a, long b, long m) {
        long ans = 0;
        //complete the function
        return ask(a,b,m);
    }
    long ask(long a,long b,long m){
        if(b==1) return a;
        long l=ask(a,b/2,m);
        
        if((b&1)!=0)
            return ((l%m*l%m)%m*a%m)%m;
        
        return (l%m*l%m)%m;
    }
}
