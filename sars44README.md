Problem Statement:

Chef is preparing his restaurant's kitchen for the day.

There are 
N
N stoves in the kitchen.
Initially, all the stoves have a temperature of 
0
0.

Every minute, the following will happen:

First, Chef can choose at most one stove and reset its temperature to 
0
0 instantly.
In particular, it is allowed to not reset the temperature of any stove, if Chef wishes to.
Then, the temperature of every stove will increase by 
1
1.
Note that it is allowed to reset the same stove multiple times (in different minutes).

Chef thinks the 
i
i-th stove is ready when its temperature is exactly 
B
i
B 
i
​
 .
Is it possible for Chef to make his choices in such a way that all 
N
N stoves are ready simultaneously?

CODE:

import java.util.*;
import java.lang.*;
import java.io.*;

class Codechef
{
	public static void main (String[] args) throws java.lang.Exception
	{
		// your code goes here
		Scanner sc=new Scanner(System.in);
		int t=sc.nextInt();
		while(t--!=0){
		    int n=sc.nextInt();
		    int a[]=new int[n];
		    int max=-1;
		    for(int i=0;i<n;i++){
		        a[i]=sc.nextInt();
		        max=Math.max(max,a[i]);
		    }
		    boolean b=false;
		    Set<Integer> st=new HashSet<>();
		    for(int i=0;i<n;i++){
		        a[i]=max-a[i];
		        if(st.contains(a[i])){
		            b=true;
		            break;
		        }
		        if(a[i]!=0)
		        st.add(a[i]);
		    }
		    if(b) System.out.println("No");
		    else System.out.println("Yes");
		    
		    
		}

	}
}

		  //  int sum=0;
		  //  if(sum%n==0) System.out.println("Yes");
		  //  else System.out.println("No");
		      //  sum+=a[i];
