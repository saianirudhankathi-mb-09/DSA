Problem Statement:

Merge two sorted linked lists and return it as a new list. 

The new list should be made by splicing together the nodes of the first two lists, and should also be sorted.


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
    public ListNode mergeTwoLists(ListNode A, ListNode B) {
        
        ListNode l=new ListNode(-99);
        ListNode t=l;
        while(A!=null  &&  B!=null){
            
            if(A.val>=B.val){
                
                t.next=new ListNode(B.val);
                B=B.next;
                t=t.next;
                
            }
            else{
                
                t.next=new ListNode(A.val);
                A=A.next;
                t=t.next;
                
            }
            
        }
        
        while(A!=null){
            t.next=new ListNode(A.val);
            A=A.next;
            t=t.next;
        }
        while(B!=null){
            t.next=new ListNode(B.val);
            B=B.next;
            t=t.next;
        }
        return l.next;
        
    }
}
