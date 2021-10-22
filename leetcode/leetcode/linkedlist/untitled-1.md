# 21. Merge Two Sorted Lists

Iteration

```
class Solution {
    public ListNode mergeTwoLists(ListNode l1, ListNode l2) {

        ListNode dummy = new ListNode (0);
        ListNode cur = dummy;
        
        while(l1 != null && l2 != null)
        {
            if(l1.val <= l2.val)
            {
                cur.next = l1;
                l1 = l1.next;
            }
            else
            {
                cur.next = l2;
                l2 = l2.next;
            }
            cur = cur.next;
        }
        
        if(l1 != null)
            cur.next = l1;
        if(l2 != null)
            cur.next = l2;
        
        return dummy.next;
    }
}
```

Recursion 

```
class Solution {
    public ListNode mergeTwoLists(ListNode l1, ListNode l2) {
        if(l1 == null)
            return l2;
        if(l2 == null)
            return l1;
        
        ListNode cur;
        if(l1.val <= l2.val)
        {
            cur = l1;
            cur.next = mergeTwoLists(l1.next,l2);
        }
        else
        {
            cur = l2;
            cur.next = mergeTwoLists(l1,l2.next);
        }
        
        return cur;
    }
}
```
