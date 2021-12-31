# LinkedList

常见算法

快慢指针

while(fast != null && fast.next != null)

Two pointer

In our previous finding cycle example, let's assume that we move the faster pointer 2 steps each time and move the slower pointer 1 step each time.

1. If there is no cycle, the fast pointer takes `N/2 times` to reach the end of the linked list, where N is the length of the linked list.
2. If there is a cycle, the fast pointer needs `M times` to catch up the slower pointer, where M is the length of the cycle in the list.

Obviously, M <= N. So we will run the loop `up to N times`. And for each loop, we only need constant time. So, the time complexity of this algorithm is `O(N)` in total.



一般 remove node用dummy





```
Reverse:
ListNode next = head.next; 
head.next = pre; 
pre = head; 
head = next;
            
典中典：
= 表示“变成”
.next = 表示“指向”
```

while里面最后一步必然要update cur

有时候会忘了cur = cur.next;



复制一个linkedlist

```
        Node dum = new Node(0);
        Node pre = dum;
        while(head != null) {
            Node node = new Node(head.val); // 复制节点 cur
            pre.next = node;               // 新链表的 前驱节点 -> 当前节点
            head = head.next;                // 遍历下一节点
            pre = node;                    // 保存当前新节点
        }
        return dum.next;
```



1 -> 2 -> 3 -> null 变成  1 -> 1 -> 2 -> 2 -> 3 - > 3 -> null

```
Node cur = head;
        while (cur != null) {
            Node copyNode = new Node(cur.val);
            copyNode.next = cur.next;
            cur.next = copyNode;
            cur = cur.next.next;
        }
```



