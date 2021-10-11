# LinkedList

Two pointer

In our previous finding cycle example, let's assume that we move the faster pointer 2 steps each time and move the slower pointer 1 step each time.

1. If there is no cycle, the fast pointer takes `N/2 times` to reach the end of the linked list, where N is the length of the linked list.
2. If there is a cycle, the fast pointer needs `M times` to catch up the slower pointer, where M is the length of the cycle in the list.

Obviously, M <= N. So we will run the loop `up to N times`. And for each loop, we only need constant time. So, the time complexity of this algorithm is `O(N)` in total.



一般 remove node用dummy

