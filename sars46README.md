Problem Statement:

Given an array of non-negative integers arr[], arrange them such that their concatenation forms the largest possible number. Return the result as a string, since it may be too large for standard integer types.

Examples:

Input: arr[] =  [3, 30, 34, 5, 9]
Output: 9534330
Explanation: The arrangement [9, 5, 34, 3, 30], gives the largest value 9534330.

Input: arr[] =  [54, 546, 548, 60]
Output: 6054854654
Explanation: The arrangement [60, 548, 546, 54], gives the largest value 6054854654.

CODE:

class Solution {
    public String findLargest(int[] arr) {
        // code here
        // Arrays.sort(arr,(int a,int b)->{
        //     String s1=a+"";
        //     String s2=b+"";
        //     return s1.charAt(0)-s2.charAt(0);
        // });
        String a[]=new String[arr.length];
        for(int i=0;i<a.length;i++){
            a[i]=String.valueOf(arr[i]);
        }
        Arrays.sort(a,(x,y)->{
            return (y+x).compareTo(x+y);
        });
        StringBuilder sb=new StringBuilder();
        if(a[0].equals("0")) return "0";
        for(String ele:a){
            sb.append(ele);
        }
        return sb.toString();
    }
}
