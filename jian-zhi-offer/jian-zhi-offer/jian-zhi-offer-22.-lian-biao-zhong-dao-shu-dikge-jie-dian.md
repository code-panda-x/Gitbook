# 剑指 Offer 22. 链表中倒数第k个节点

My dumb ans:

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
    public ListNode getKthFromEnd(ListNode head, int k) {
        if(head == null)
            return null;

        int size = 0;
        ListNode res = head;
        while(head != null)
        {
            size++;
            head = head.next;
        }

        for(int i = 0; i < size-k; i++)
        {
            res = res.next;
        }
        return res;
    }
}
```

快慢指针

```
class Solution {
    public ListNode getKthFromEnd(ListNode head, int k) {
        ListNode former = head, latter = head;
        for(int i = 0; i < k; i++)
            former = former.next;
        while(former != null) {
            former = former.next;
            latter = latter.next;
        }
        return latter;
    }
}


```
