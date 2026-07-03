Problem Statement:

Given an array nums, return true if the array was originally sorted in non-decreasing order, then rotated some number of positions (including zero). Otherwise, return false.

There may be duplicates in the original array.

Note: An array A rotated by x positions results in an array B of the same length such that B[i] == A[(i+x) % A.length] for every valid index i.

CODE:

class Solution {
    public boolean check(int[] nums) {
        int a[]=new int[nums.length];
        boolean b=false;
        int k=0,idx=0,l=0;

        for(int i=1;i<nums.length;i++){
            
            if(nums[i]<nums[i-1]){
                b=true;
                k=i;
                idx=i;
            }

        }

        if(!b) return true;

        while(k<nums.length){
            a[l++]=nums[k++];
        }

        k=0;

        while(k<idx){
            a[l++]=nums[k++];
        }

        for(int i=1;i<nums.length;i++){
            if(a[i]<a[i-1]) return false;
        }

         return true;

    }
}
