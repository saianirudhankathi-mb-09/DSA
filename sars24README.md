Problem Statement:


Say you have an array, A, for which the ith element is the price of a given stock on day i.

Design an algorithm to find the maximum profit.

You may complete as many transactions as you like (i.e., buy one and sell one share of the stock multiple times).

However, you may not engage in multiple transactions at the same time (ie, you must sell the stock before you buy again).

CODE:

public class Solution {

    // DO NOT MODIFY THE LIST. IT IS READ ONLY
    public int maxProfit(final List<Integer> A) {

        if (A.size() == 0) return 0;

        int ch = A.get(0);
        int p = 0;

        for (int i = 1; i < A.size(); i++) {

            if (ch < A.get(i)) {
                p += A.get(i) - ch;
                ch = A.get(i);
            }

            ch = Math.min(ch, A.get(i));
        }

        return p;
    }
}
