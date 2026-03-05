Problem Statement:

Given an array nums of size n and an integer k, find the length of the longest sub-array that sums to k. If no such sub-array exists, return 0.

CODE:

class Solution {
    public int longestSubarray(int[] a, int k) {
       Map<Integer,Integer> m=new HashMap<>();
       int max=0;
       if(a[0]==k) max=1;
       for(int i=1;i<a.length;i++){
            a[i]+=a[i-1];
            if(a[i]==k) max=i+1;
       }
       for(int i=0;i<a.length;i++){
            if(m.containsKey(a[i]-k)){
                max=Math.max(max,i-m.get(a[i]-k));
            }
            if(!m.containsKey(a[i])) m.put(a[i],i);
       }
       return max;
    }
}
