# 剑指 Offer 24. 反转链表

Two pointers&#x20;

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
    public ListNode reverseList(ListNode head) {
        ListNode prev = null;
        ListNode cur = head;
        if(head == null)
            return null;
        
        while(cur != null)                // 简而言之：1. 往回指 2.更新两个指针
        {
            ListNode next = cur.next;    // 暂存下一个node
            cur.next = prev;                // 当前node指向null(前一个node)
            prev = cur;                    // 右移 prev

            cur = next;                    // 右移 cur  指向原本的下一个node
        }
        return prev;
    }
}


```

Recursion

```
class Solution {
    public ListNode reverseList(ListNode head) {
        return recur(head, null);    // 调用递归并返回
    }
    private ListNode recur(ListNode cur, ListNode pre) {
        if (cur == null) return pre; // 终止条件
        ListNode res = recur(cur.next, cur);  // 递归后继节点
        cur.next = pre;              // 修改节点引用指向
        return res;                  // 返回反转链表的头节点
    }
}


```
