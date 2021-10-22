---
description: 好好消化
---

# \*\*\*剑指 Offer 18. 删除链表的节点

用dummy: 是因为head也要check

```
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
class Solution {
    public ListNode deleteNode(ListNode head, int val) {
        if (head == null)
            return null;

        ListNode dummy = new ListNode(0,head);
        ListNode cur = dummy;

        while(cur.next != null)
        {
            if(cur.next.val == val)
                cur.next = cur.next.next;
            else
                cur = cur.next;
        }

        return dummy.next;
    }
}

```

2 Iteration 

```
class Solution {
    public ListNode deleteNode(ListNode head, int val) {
        if(head.val == val) return head.next;
        ListNode pre = head, cur = head.next;
        while(cur != null && cur.val != val) {
            pre = pre.next; // or pre = cur
            cur = cur.next;
        }
        if(cur != null) pre.next = cur.next;
        return head;
    }
}


```

3\.

Recursion:

```
class Solution {
    public ListNode deleteNode(ListNode head, int val) {
        if (head == null) {
            return null;
        }
        if (head.val == val) {
            return head.next;
        } else {
            head.next = deleteNode(head.next, val);
        }
        return head;
    }
}
```
