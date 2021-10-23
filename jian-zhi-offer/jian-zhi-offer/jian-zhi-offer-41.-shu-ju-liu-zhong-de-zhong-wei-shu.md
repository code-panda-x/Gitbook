---
description: 吊逼方法，自己想不到
---

# 剑指 Offer 41. 数据流中的中位数 1

用大顶堆+小顶堆方法，可以看作大顶堆是普通班，小顶堆是实验班。数量上时刻保持 小顶-大顶<=1（两堆相等或者小顶比大顶多一个）。

新学生先入普通班（大顶堆），此时可能会失去平衡了，于是取大顶堆的第一个（班里最好的学生）加入实验班（小顶堆），判断若数量过多（不是等于或多一个），取第一个（实验班里最差的学生）到普通班（大顶堆）里。 取中位数的时候，若两堆数量相等，则各取堆顶取平均，若小顶比大顶多一，则多的那一个就是中位数。

```
class MedianFinder {
    PriorityQueue<Integer> left;//大顶
    PriorityQueue<Integer> right;//小顶
    public MedianFinder() {
        left=new PriorityQueue<>((n1,n2)->n2-n1);
        right=new PriorityQueue<>();
    }
    public void addNum(int num) {
        left.add(num);
        right.add(left.poll());
        if(left.size()+1<right.size())
            left.add(right.poll());
    }
    public double findMedian() {
        if(right.size()>left.size())return right.peek();
        return (double)(left.peek()+right.peek())/2;
    }
}
```



