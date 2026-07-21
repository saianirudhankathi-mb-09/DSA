Problem Statement:

Given a root of binary search tree and a key(node) value, find the floor and ceil value for that particular key value.



Floor Value Node: Node with the greatest data lesser than or equal to the key value. 


Ceil Value Node: Node with the smallest data larger than or equal to the key value.


If a particular floor or ceil value is not present then output -1.

CODE:

/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int data;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode(int val) { data = val; left = null, right = null }
 * }
 **/

class Solution {
    public List<Integer> floorCeilOfBST(TreeNode root, int key) {
        //your code goes here
        List<Integer> ans=new ArrayList<>();
        int a1=-1,a2=-1;
        int l=floor(root,key,a1),r=ceil(root,key,a2);
        ans.add(l);
        ans.add(r);
        return ans;
    }

    int floor(TreeNode r,int val,int ans){
        if(r==null) return ans;
        if(r.data==val) return ans=val;
        if(r.data<val){
            ans=r.data;
            return floor(r.right,val,ans);
        }
        return floor(r.left,val,ans);
    }
    int ceil(TreeNode r,int val,int ans){
        if(r==null) return ans;
        if(r.data==val) return ans=val;
        if(r.data>val){
            ans=r.data;
            return ceil(r.left,val,ans);
        }
        return ceil(r.right,val,ans);
    }

}
