---
description: 做过，忘了，我是傻逼
---

# 19. Remove Nth Node From End of List

快慢双指针

让快指针先走n步，再一起移动slow fast。当fast为null，slow为倒数第n个node

```
class Solution {
    public ListNode removeNthFromEnd(ListNode head, int n) {
        ListNode dummy = new ListNode(0,head);
        ListNode fast = head;
        ListNode slow = dummy;
        
        for(int i = 0; i < n; i++)
            fast = fast.next;
        
        while(fast != null)
        {
            slow = slow.next;
            fast = fast.next;
        }
        slow.next = slow.next.next;
        return dummy.next;
}
}
```
