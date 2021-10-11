---
description: 做对了一半，错误在于使用 if(l1.next == null)
---

# 剑指 Offer 52. 两个链表的第一个公共节点

浪漫相遇，也可以用hashset

插个楼，很多童鞋会在最后一步有疑惑，感觉会陷入死循环，实际上不会，因为最后两人同时走到末尾，都是 None，就结束循环了。感谢☺

如果没有交集，走了l1和l2，交换赛道后，两node会齐头并进，在l1+l2 的位置处共同来到null，退出循环

```
public class Solution {
    public ListNode getIntersectionNode(ListNode headA, ListNode headB) {
        if(headA == null || headB == null)
            return null;
        
        ListNode l1 = headA;
        ListNode l2 = headB;

        while(l1 != l2)
        {
                
            if(l1 == null)
                l1 = headB;
            else
                l1 = l1.next;

            if(l2 == null)
                l2 = headA;
            else
                l2 = l2.next;

        }
        return l1;
    }
}
```

