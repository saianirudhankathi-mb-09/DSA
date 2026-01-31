Problem Statement:

You are given a string s consisting of lowercase English letters and special characters.

Your task is to perform these in order:

Reverse the lowercase letters and place them back into the positions originally occupied by letters.
Reverse the special characters and place them back into the positions originally occupied by special characters.
Return the resulting string after performing the reversals.©leetcode

CODE:

class Solution {
    public String reverseByType(String s) {
        StringBuilder sb1=new StringBuilder();
        StringBuilder sb2=new StringBuilder();
        for(char ch:s.toCharArray()){

            if(ch>=97  &&  ch<=122){ sb1.append(ch);}
            else{ sb2.append(ch);}
            
        }
        // System.out.println(sb1+"abc"+sb2);
        String str1=sb1.reverse().toString();
        String str2=sb2.reverse().toString();
        StringBuilder ans=new StringBuilder();

        int i=0,j=0;
        for(char ch:s.toCharArray()){
            
            if(ch>=97  &&  ch<=122){
                ans.append(str1.charAt(i));
                i++;
            }
            else{
                ans.append(str2.charAt(j));
                j++;
            }
        }

        return ans.toString();

    }
}©leetcode
