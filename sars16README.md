Problem Statement:

Given a Binary tree. You have to count and return the number of Non-leaf nodes present in it.

CODE:

import java.util.*;
class BTNode
{
    int data;
    BTNode left, right;
    BTNode(int d)
    {
      	data = d;
      	left = right = null;
    }
}

class BeingZero
{
    int countNonLeafNodes(BTNode root)
    {
      // TODO:  Your Code Goes Here
        if(root==null) return 0;
        
        if(root.left==null  &&  root.right==null) return 0;
        

        return 1+countNonLeafNodes(root.left)+countNonLeafNodes(root.right);
    }
}
