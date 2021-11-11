# HEAP

PriorityQueue: 说白了就是加进去一组数它自动帮你排序，每次poll的是数组里面最小的数。（Min Heap）

![](<../../.gitbook/assets/image (26).png>)



看到 Kth largest/smallest 应该想到用heap:&#x20;

&#x20;   Kth largest: minHeap，每次把最小的挤出去，遍历完所有元素，留下的是k个最大的，peek的则是第K大的

&#x20;   Kth smallest: maxHeap，每次把最大的挤出去，遍历完所有元素，留下的是k个最小的，peek的则是第K小的

In summary, a heap:

* Stores elements, and can find the smallest (min-heap) or largest (max-heap) element stored in O(1)
* Can add elements and remove the smallest (min-heap) or largest (max-heap) element in O(log(n))
* Can perform insertions and removals while always maintaining the first property.
