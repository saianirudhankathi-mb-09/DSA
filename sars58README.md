Problem Statement:

Given a 1-indexed array of integers numbers that is already sorted in non-decreasing order, find two numbers such that they add up to a specific target number. Let these two numbers be numbers[index1] and numbers[index2] where 1 <= index1 < index2 <= numbers.length.

Return the indices of the two numbers index1 and index2, each incremented by one, as an integer array [index1, index2] of length 2.

The tests are generated such that there is exactly one solution. You may not use the same element twice.

Your solution must use only constant extra space.

CODE:

class Solution {
    public int[] twoSum(int[] n, int t) {
        for(int i=0;i<n.length;i++){
            int ans=bs(n,i,t-n[i]);
            if(ans!=-1) return new int[]{i+1,ans+1};
        }
        return new int[]{-1,-1};
    }
    int bs(int a[],int idx,int req){
        int l=0,h=a.length-1;
        while(l<=h){
            int m=l+(h-l)/2;
            if(idx!=m  &&  a[m]==req) return m;
            else if(a[m]<=req) l=m+1;
            else h=m-1;
        }
        return -1;
    }
}
