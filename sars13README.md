Problem Statement:

You are given a string S of length N. Return the total number of substrings of S, which contain only the
letters 'x' and 'y'.
For Example:
Let N = 5 S = "axxny".
Substrings are "x", "x", "xx", and "y".
So our answer is 4.

CODE:

import java.io.*;
import java.util.*;

class BeingZero {
    public long solve(int n, String s) {
        // write your code here
        long ans=0;
        long ct=0;
        // List<Integer> l=new ArrayList<>();
        for(char ch:s.toCharArray()){
            if(ch=='x'  ||  ch=='y'){
                ct++;
            }
            else{
                if(ct!=0){
                    ans+=(ct*(ct+1))/2;
                }
                ct=0;
            }
        }
        if(ct!=0){
            // ans+=2*ct-1;
            ans+=(ct*(ct+1))/2;
        }
        return ans;
    }
}
