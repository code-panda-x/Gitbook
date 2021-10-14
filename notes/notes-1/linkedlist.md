# LinkedList

常见算法

快慢指针





```
ListNode next = head.next; 
head.next = pre; 
pre = head; 
head = next;
            
典中典：
= 表示“变成”
.next = 表示“指向”
```

有时候会忘了cur = cur.next;

