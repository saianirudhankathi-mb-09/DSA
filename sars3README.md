Problem Statement:

Merge k sorted linked lists and return it as one sorted list.

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
	public ListNode mergeKLists(ArrayList<ListNode> a) {
        
        PriorityQueue<Integer> pq=new PriorityQueue<>();
        
        for(ListNode t:a){
            while(t!=null){
                pq.add(t.val);
                t=t.next;
            }
        }
        
        ListNode l=new ListNode(-99);
        ListNode nl=l;
        
        while(!pq.isEmpty()){
            
            nl.next=new ListNode(pq.poll());
            nl=nl.next;
            
        }
        
        return l.next;
        
	}
}
