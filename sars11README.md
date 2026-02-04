Problem Statement:

You are given an array A of length N. Your task is to append a non-negative integer X to the array A such that the BITWISE OR of the entire array becomes Y. Find the minimum possible value for X, output -1 if it doesn't exist

CODE:

class BeingZero {
    public int solve(int A[] , int Y) {
        int ans = 0;
        //complete the function

        for(int k=0;k<32;k++){

            int ct=0;
            for(int i=0;i<A.length;i++){

                // ct|=A[i]&(1<<k);
                if((A[i]&(1<<k))!=0){
                    ct=1;
                    break;
                }
                
            }

            if((Y&(1<<k))==0  &&  ct==1) return -1;
            // if((Y&(1<<k))==1  &&  ct==0) (ans&(1<<k))=1;
            if((Y&(1<<k))!=0  &&  ct==0) ans=(ans|(1<<k));

        }

        return ans;
    }
}
