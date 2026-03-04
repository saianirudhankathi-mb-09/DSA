Problem Statement:

There are 
N
N friends at a party playing a game called Balloon Smash. Each friend 
i
i has an annoyance factor 
A
i
A 
i
​
 .

If the 
i
i-th friend is hit by 
A
i
A 
i
​
  balloons, they immediately leave the party.

The game proceeds according to the following rules:

The friends take turns sequentially from 
1
1 to 
N
N.
If the current friend has already left the party, the turn moves to the next friend.
If there is no next friend available, the game ends.
When it is friend 
i
i's turn and they are still present in the party:
Friend 
i
i hits every other friend currently present in the party with exactly one balloon.
After doing so, friend 
i
i leaves the party.
Then, for any remaining friend 
j
j who has been hit by 
A
j
A 
j
​
  balloons so far, this friend will immediately leave the party.
Your task is to determine how many balloons hit each friend by the time the party ends.

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
		    
		    int arr[]=new int[n];
		    int ans[]=new int[n];
		    
		    for(int i=0;i<n;i++){
		        arr[i]=sc.nextInt();
		    }
		    
		    int ct=1;
		    
		    for(int i=1;i<n;i++){
		        ans[i]=Math.min(ct,arr[i]);
		        if(arr[i]-ct>0) ct++;
		    }
		    
		    for(int ele:ans) System.out.print(ele+" ");
		    System.out.println();
		    
		}
	}
}

		      //  if(!b[i]){
		      //      b[i]=true;
		          //  for(int k=i+1;k<n;k++){
		          //      if(!b[k]){
		          //          ans[k]+=1;
		          //          if(ans[k]==arr[k]){
		          //              b[k]=true;
		          //          }
		          //      }
		          //  }
		      //  }
		                  //st.remove(k);
		  //  boolean b[]=new boolean[n];
		  //  Set<Integer> st=new HashSet<>();
		    
		  //  for(int i=0;i<n;i++){
		  //      st.add(i);
		  //  }
		    
		  //  int ans[]=new int[n];
		    
		  //  for(int i=0;i<n;i++){
		  //      if(st.contains(i)){
    // 		          st.remove(i);
    		          
    // 		          List<Integer> l=new ArrayList<>();
    		          
    // 		          for(int k:st){
    // 		              ans[k]+=1;
    // 		              if(ans[k]==arr[k]){
    // 		                  l.add(k);
    // 		              }
    // 		          }
    		          
    // 		          for(int ele:l) st.remove(ele);
		  //        }
		  //  }
		    
		  //  for(int ele:ans){
		  //      System.out.print(ele+" ");
		  //  }
		  //  System.out.println();
