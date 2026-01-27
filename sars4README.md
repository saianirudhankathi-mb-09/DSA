Problem Statement:

Given a singly linked list

    L: L0 → L1 → … → Ln-1 → Ln,
reorder it to:

    L0 → Ln → L1 → Ln-1 → L2 → Ln-2 → …
You must do this in-place without altering the nodes’ values.

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
    public ListNode reorderList(ListNode A) {
        
        if(A==null  ||  A.next==null) return A;
        
        int ct=count(A);
        
        ct=(ct-1)/2;
        
        ListNode t=A,p=A;
        
        while(ct-->=0){
            
            if(p!=t) p=p.next;
            t=t.next;
            
        }
        
        p.next=null;
        t=reverse(t);
        
        ListNode j=t,t2=t.next,i=A,t1=A.next;
        
        while(i!=null  &&  j!=null){
            
            i.next=j;
            j.next=t1;
            i=t1;
            if(t1==null) return A;
            t1=t1.next;
            j=t2;
            if(t2==null) return A;
            t2=t2.next;
            
        }
        
        return A;
        
    }
    
    
    public ListNode reverse(ListNode l){
        
        // if(l==null  ||  l.next==null) return l;
        
        // int ct=count(l);
        
        // ct=ct/2;
        // ListNode t=l,p=l;
        // while(ct--!=0){
            
        //     if(p!=t) p=p.next;
        //     t=t.next;
            
        // }
        
        // p.next=null;
        
        // ListNode left=reverse(l);
        // ListNode right=reverse(t);
        // right.next=left;
        
        // return right;
        
        ListNode prev=null,curr=l;
        
        while(curr!=null){
            
            ListNode next=curr.next;
            curr.next=prev;
            prev=curr;
            curr=next;
            
        }
        
        return prev;
        
    }
    
    public int count(ListNode l){
        
        int ct=0;
        ListNode t=l;
        
        while(t!=null){
            ct++;
            t=t.next;
        }
        
        return ct;
        
    }
    
}
