Problem Statement:

Given an integer array nums of unique elements, return all possible subsets (the power set).

The solution set must not contain duplicate subsets. Return the solution in any order.

CODE:

class Solution {
    public List<List<Integer>> subsets(int[] nums) {
        List<List<Integer>> ans=new ArrayList<>();
        for(int m=0;m<(1<<nums.length);m++){
            List<Integer> sub=new ArrayList<>();
            for(int i=0;i<nums.length;i++){
                if((m&1<<i)!=0) sub.add(nums[i]);
            }
            ans.add(sub);
        }
        return ans;
    }
}
