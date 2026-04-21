Problem Statement:

Given a triangle array, return the minimum path sum from top to bottom.

For each step, you may move to an adjacent number of the row below. More formally, if you are on index i on the current row, you may move to either index i or index i + 1 on the next row.

CODE:

class Solution {
    public int minimumTotal(List<List<Integer>> t) {
        for(int i=1;i<t.size();i++){
            t.get(i).set(0,t.get(i-1).get(0)+t.get(i).get(0));
            t.get(i).set(t.get(i).size()-1,t.get(i-1).get(t.get(i-1).size()-1)+t.get(i).get(t.get(i).size()-1));
        }
        for(int i=2;i<t.size();i++){
            for(int j=1;j<t.get(i).size()-1;j++){
                t.get(i).set(j,t.get(i).get(j)+Math.min(t.get(i-1).get(j),t.get(i-1).get(j-1)));
            }
        }
        int min=Integer.MAX_VALUE;
        for(int i=0;i<t.get(t.size()-1).size();i++){
            min=Math.min(min,t.get(t.size()-1).get(i));
        }
        return min;
    }
}
