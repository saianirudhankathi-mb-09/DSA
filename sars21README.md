Problem Statement:

You are given an array of strings words, where each string represents a word containing lowercase English letters.

You are also given an integer array weights of length 26, where weights[i] represents the weight of the ith lowercase English letter.

The weight of a word is defined as the sum of the weights of its characters.

For each word, take its weight modulo 26 and map the result to a lowercase English letter using reverse alphabetical order (0 -> 'z', 1 -> 'y', ..., 25 -> 'a').

Return a string formed by concatenating the mapped characters for all words in order.

CODE:

class Solution {
    public String mapWordWeights(String[] w, int[] wt) {

        StringBuilder sb=new StringBuilder();

        for(String str:w){

            int sum=0;

            for(char ch:str.toCharArray()){
                sum+=wt[ch-'a'];
            }

            sum%=26;

            sb.append((char)(25-sum+97));

        }

        return sb.toString();
        
    }
}
