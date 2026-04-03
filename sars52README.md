Problem Statement:

M people are going on an adventure, and need to decide how to divide their food resources.

There are 
N
N types of food items with them, the 
i
i-th food type having 
A
i
A 
i
​
  units. A single person needs to eat one unit of food in one day.

Each person must eat a single type of food for the entire duration of the adventure. Different people may eat the same, or different types of food.

The duration of the adventure is not yet decided, but this friend group wants to go for as many days as possible. What is the maximum number of days where they will not run out of food, while satisfying the constraint?

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
		int n=sc.nextInt();
		int m=sc.nextInt();
		int a[]=new int[n];
		for(int i=0;i<n;i++){
		    a[i]=sc.nextInt();
		}
		int min=Integer.MIN_VALUE;
		Arrays.sort(a);
		int l=1,h=a[a.length-1];
		while(l<=h){
		    int mid=l+(h-l)/2;
		    int ct=0;
		    for(int ele:a) ct+=ele/mid;
		    if(ct>=m){ 
		        l=mid+1;
		        min=Math.max(min,mid);
		    }
		    else {
		        h=mid-1;
		    }
		}
		if(min!=Integer.MIN_VALUE) System.out.println(min);
		else System.out.println(0);

	}
}
