Problem Statement:

Given a sorted array of nums and an integer x, write a program to find the lower bound of x.



The lower bound algorithm finds the first and smallest index in a sorted array where the value at that index is greater than or equal to a given key i.e. x.



If no such index is found, return the size of the array.


Example 1

Input : nums= [1,2,2,3], x = 2

Output:1

Explanation:

Index 1 is the smallest index such that arr[1] >= x.

CODE:

class Solution {
    public int lowerBound(int[] nums, int x) {
       int ans=nums.length;
       int l=0,h=nums.length-1;
       while(l<=h){
            int m=(h-l)/2+l;
            if(nums[m]>=x){
                ans=m;
                h=m-1;
            }
            else{
                l=m+1;
            }
       }
       return ans;
    }
}
