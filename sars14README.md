Problem Statement:

Given a number, swap the adjacent bits in the binary representation of the number, and print the new number formed after swapping.

CODE:

class BeingZero{
	public int solve(int n){
	    //Input and output are handled complete the function and return the required answer
	    int ans = 0;

        for(int k=0;k<32;k+=2){

            int t1=0,t2=0;
            t1=((n&(1<<k))==0)?0:1;
            t2=((n&(1<<(k+1)))==0)?0:1;
            // t2|=(n&(1<<(k+1));
            // n=(n&(1<<k))&(n&(1<<(k+1)));
            // n=(n&(1<<(k+1)))&t;

            if(t1!=t2){
                n^=~(1<<k);
                n^=~(1<<(k+1));
                
            }
            

        }

	    return n;
	}
}
