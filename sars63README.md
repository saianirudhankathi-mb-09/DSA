Problem Statament:

A parentheses string is valid if and only if:

It is the empty string,
It can be written as AB (A concatenated with B), where A and B are valid strings, or
It can be written as (A), where A is a valid string.
You are given a parentheses string s. In one move, you can insert a parenthesis at any position of the string.

For example, if s = "()))", you can insert an opening parenthesis to be "(()))" or a closing parenthesis to be "())))".
Return the minimum number of moves required to make s valid.

CODE:

class Solution {
    public int minAddToMakeValid(String s) {

        Stack<Character> st=new Stack<>();


        for(char ch:s.toCharArray()){

            if(ch=='('){
                st.add('(');
            }

            else if(ch==')'){
                if(!st.isEmpty()  &&  st.peek()=='('){
                    st.pop();
                }
                else{
                    st.push(')');
                }
            }

        }

        return st.size();


    }
}
        // int l=0,r=0;

        // for(char ch:s.toCharArray()){

        //     if(ch=='(') l++;
        //     if(ch==')') r++;

        // }

        // return Math.abs(l-r);
