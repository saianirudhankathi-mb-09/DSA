Problem Statement:

Ankit is creating the lexicographically smallest possible binary string of length K such that there are exactly 'K' ones, each with exactly one zero in both adjacent positions.
Your task is to find such a string. If it's not possible, return the string "0".

CODE:

import java.util.*;

class BeingZero { 
    public String solve(int n, int k) {
        //complete the function
        if(k*2>=n) return "0";
        // else{
            StringBuilder sb=new StringBuilder();
            int rem=n-2*k;
            while(k--!=0){
                sb.append("01");
            }
            while(rem--!=0){
                sb.append("0");
            }
        return sb.reverse().toString();
        // }
    }
}
