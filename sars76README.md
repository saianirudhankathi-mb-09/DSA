Problem Statement:

Given an integer array nums, rotate the array to the right by k steps, where k is non-negative.

CODE:

class Solution {
    public void rotate(int[] nums, int k) {
        int na[]=new int[nums.length];
        for(int i=0;i<nums.length;i++){
            na[(i+k)%nums.length]=nums[i];
        }
        for(int i=0;i<nums.length;i++){
            nums[i]=na[i];
        }
    }
}
