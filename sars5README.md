Problem Statement:
Reverse a linked list from position m to n. Do it in-place and in one-pass.

For example:

Given 1->2->3->4->5->NULL, m = 2 and n = 4,

return 1->4->3->2->5->NULL.

CODE:

/**
 * Definition for singly-linked list.
 * class ListNode {
 *     public int val;
 *     public ListNode next;
 *     ListNode(int x) { val = x; next = null; }
 * }
 */
public class Solution {
    public ListNode reverseBetween(ListNode A, int m, int n) {
        
        if(m==n) return A;
        
        m-=1;
        
        ListNode f=A,s=A,p2=A,p1=A;
        
        while(n--!=0){
            
            if(p2!=s) p2=p2.next;
            s=s.next;
            
        }
        p2.next=null;
        if(m!=0){
            while(m--!=0){
                if(p1!=f) p1=p1.next;
                f=f.next;
            }
            p1.next=null;
        }
        ListNode rev=reverse(f);
        ListNode t=rev;
        while(t.next!=null) t=t.next;
        t.next=s;
        if(p1==f) return rev;
        p1.next=rev;
        
        return A;
        
    }
    
    ListNode reverse(ListNode A){
        
        ListNode prev=null,curr=A;
        
        while(curr!=null){
            
            ListNode next=curr.next;
            curr.next=prev;
            prev=curr;
            curr=next;
            
        }
        
        return prev;
        
    }
}
