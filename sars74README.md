Problem Statement:

There are 
N
N people wanting to enter a movie theatre, however the movie theatre has a weird rule, the people have to enter in order that they bought the tickets.

The people are indexed 
1
1 through 
N
N based on when they bought the ticket.

The 
i
i-th person shows up at time 
A
i
A 
i
​
 , but he may have to wait for others till he is allowed to enter the movie theatre. Assume that you can enter instantly otherwise.

Given the times when the people will arrive, find the total wait time of everyone.

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
		    int g[]=new int[n];
		    int max=-1;long ct=0;
		    for(int i=0;i<n;i++){
		        
		        a[i]=sc.nextInt();
		        
		        if(max<a[i]){
		            g[i]=a[i];
		            max=a[i];
		        }
		        else g[i]=max;
		        
		        ct+=g[i]-a[i];
		        
		    }
		    System.out.println(ct);
		}

	}
}
