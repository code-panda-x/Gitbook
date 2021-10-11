---
description: 对于理解next 和 = 非常好
---

# 328. Odd Even Linked List

分割后合并

```
class Solution {
    public ListNode oddEvenList(ListNode head) {
        if(head == null)
            return null;
        
        ListNode odd = head;
        ListNode even = head.next;
        ListNode evenhead = even;
        
        while(even != null && even.next != null)
        {
            odd.next = odd.next.next;
            odd = odd.next;
            even.next = even.next.next;
            even = even.next;
        }
        odd.next = evenhead;
        
        return head;
    }
}
```
