Problem Statement:

Given an array nums of size n, return the majority element.

The majority element is the element that appears more than ⌊n / 2⌋ times. You may assume that the majority element always exists in the array.

CODE:

class Solution {
    public int majorityElement(int[] nums) {
        Map<Integer,Integer> m=new HashMap<>();
        for(int ele:nums){
            m.put(ele,m.getOrDefault(ele,0)+1);
            if(m.get(ele)>nums.length/2) return ele;
        }
        return -1;
    }
}
