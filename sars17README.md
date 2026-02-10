Problem Statement:

Given root of a Binary Search Tree and check if its a complete tree. In a complete binary tree every level, except possibly the last, is completely filled, and all nodes in the last level are as far left as possible.

CODE:

import java.util.*;

class BSTNode{
    int val;
    BSTNode left, right;
    BSTNode(int d){
      	val = d;
      	left = right = null;
    }
}

class BeingZero
{
    boolean solve(BSTNode root)
    {
      // TODO:  Your Code Goes Here

        if(root==null) return true;

        if(root.left==null  &&  root.right==null) return true;

        int ct=count(root);

        return ask(root,0,ct);

    }

    boolean ask(BSTNode root,int i,int ct){

        if(root==null) return true;

        if(i>=ct) return false;

        // if(root.left==null  &&  root.right==null  &&  i<ct) return true;

        return ask(root.left,2*i+1,ct)&&ask(root.right,2*i+2,ct);

    }

    int count(BSTNode root){

        if(root==null) return 0;
        
        return 1+count(root.left)+count(root.right);

    }

}

