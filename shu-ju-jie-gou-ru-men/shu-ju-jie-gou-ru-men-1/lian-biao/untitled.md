# 206. Reverse Linked List

My stupid ans

```

/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode reverseList(ListNode head) {
        if(head == null)
            return null;
        ListNode res = new ListNode();
        res = head;
        ListNode x = res;
        List<Integer> arr = new ArrayList();

        while(head != null)
        {
            arr.add(head.val);
            head = head.next;
        }
        for(int i = arr.size() - 1; i >=0; i--)
        {
            //System.out.println(arr.get(i));
            res.val = arr.get(i);
            res = res.next;
        }
        return x;
    }
}

```

Iteration:

```
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode reverseList(ListNode head) {
        if(head == null)
            return null;

        ListNode cur = head;
        ListNode prev = null;

        while(cur != null)
        {
            ListNode next = cur.next;
            cur.next = prev;
            prev = cur;

            cur = next;
        }
        return prev;
    }
}
```

Recursion:

```
public ListNode reverseList(ListNode head) {
    // 1. 递归终止条件
    if (head == null || head.next == null) {
        return head;
    }
    ListNode p = reverseList(head.next);
    head.next.next = head;
    head.next = null;
    return p;
}

```

![](<../../../.gitbook/assets/image (11).png>)
