# LinkedList

常见算法

快慢指针





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

