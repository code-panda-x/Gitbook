---
description: 数学法想不明白
---

# 剑指 Offer 62. 圆圈中最后剩下的数字

想到了此解法，没有自己写出来

 模拟链表

```
class Solution {
    public int lastRemaining(int n, int m) {
        List<Integer> arr = new ArrayList<>();

        for(int i = 0; i < n; i++)
            arr.add(i);
        
        int index = 0;
        while(n > 1)
        {
            index = (index + m - 1) % n;
            arr.remove(index);
            n--;
        }
        return arr.get(0);
    }
}
```

数学法

