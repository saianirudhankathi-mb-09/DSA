Problem Statement:

Given an integer n, return the number of prime numbers that are strictly less than n.

CODE:

class Solution {
    public int countPrimes(int n) {

        int a[]=new int[n];

        for(int i=0;i<n;i++){
            a[i]=i;
        }

        int ct=0;

        for(int i=2;i*i<n;i++){

            if(a[i]==i){

                // ct++;

                for(int j=i*i;j<n;j+=i){
                    a[j]=i;
                }

            }

        }

        for(int i=2;i<n;i++){

            if(a[i]==i) ct++;

        }

        return ct;
        
    }
}
