Problem Statement:

You have a number N and Q queries.
1 X: means print value of Xth bit in N. (value can be 0 or 1)
2 X: means change Xth bit of N to 1, and then print N.
3 X: means change Xth bit of N to 0, and then print N.
4 X: means toggle Xth bit of N and then print N, toggle means change 0 to 1 vice versa.

CODE:

import java.util.*;
import java.io.*;

class Main {
    public static void main(String[] args) {
        Scanner sc=new Scanner(System.in);
        int t=sc.nextInt();
        while(t--!=0){

            int q=sc.nextInt();
            int n=sc.nextInt();

            while(q--!=0){

                int a=sc.nextInt();
                int k=sc.nextInt();

                switch(a){

                    case 1:
                        // int k=sc.nextInt();
                        System.out.println((n&(1<<k))!=0?1:0);
                        break;
                    case 2:
                        n|=(1<<k);
                        System.out.println(n);
                        break;
                    case 3:
                        n&=~(1<<k);
                        
                        System.out.println(n);
                        break;
                    case 4:
                        n^=(1<<k);
                        System.out.println(n);
                        break;
                        
                }
                
            }
            
        }
    }
}
