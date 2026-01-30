Problem Statement:

Given a binary tree, determine if it is a valid binary search tree (BST).

Assume a BST is defined as follows:

The left subtree of a node contains only nodes with keys less than the node’s key.
The right subtree of a node contains only nodes with keys greater than the node’s key.
Both the left and right subtrees must also be binary search trees.

CODE:

/**
 * Definition for binary tree
 * class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode(int x) {
 *      val = x;
 *      left=null;
 *      right=null;
 *     }
 * }
 */
public class Solution {
    public int isValidBST(TreeNode A) {
        
        List<Integer> l1=new ArrayList<>();
        List<Integer> l2=new ArrayList<>();
        
        ask(A,l1,l2);
        
        Collections.sort(l2);
        
        for(int i=1;i<l1.size();i++){
            
            if(l1.get(i)<=l1.get(i-1)) return 0;
            
        }
        // if(l1.equals(l2))
        //     return 1;
        return 1;
    }
    
    public void ask(TreeNode root,List<Integer> l1,List<Integer> l2){
        
        if(root==null) return;
        
        // if(root.left==null &&  root.right==null){
        //     l1.add(root.val);
        //     l2.add(root.val);
        //     return;
        // }
        
        // if(root.left!=null){
        // }
            ask(root.left,l1,l2);
        
        l1.add(root.val);
        l2.add(root.val);
        
            ask(root.right,l1,l2);
        // if(root.right!=null){
        // }
        
        return;
        
    }
}
