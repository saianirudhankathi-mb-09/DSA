Problem Statement:

Vacation Excitement
Chef has planned a vacation with his friends in the month of March, and is really looking forward to it!

The vacation begins on the 
X
X-th of March.

As days get closer to the vacation date, Chef gets more and more excited for it.
Chef's excitement level starts at 
Y
Y on March 
1
1. It will then increase by 
1
1 for every day that passes; so it will be 
Y
+
1
Y+1 on March 
2
2-nd, 
Y
+
2
Y+2 on March 
3
3-rd, and so on.

What will Chef's excitement level be on the day the vacation begins?

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
		int x=sc.nextInt();
		int y=sc.nextInt();
// 		if(x==1) System.out.println(y);
// 		else 
		System.out.println(y+x-1);

	}
}
