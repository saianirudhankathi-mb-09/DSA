Problem Statement:

Given an integer array nums, return true if any value appears at least twice in the array, and return false if every element is distinct.

CODE:

class Solution {
    public boolean containsDuplicate(int[] nums) {
        Set<Integer> st=new HashSet<>();
        for(int ele:nums){
            if(st.contains(ele)) return true;
            st.add(ele);
        }
        return false;
    }
}
