---
description: >-
  https://leetcode-cn.com/problems/fei-bo-na-qi-shu-lie-lcof/solution/mian-shi-ti-10-i-fei-bo-na-qi-shu-lie-dong-tai-gui/
---

# 剑指 Offer 10- I. 斐波那契数列

暴力法：超时

```
class Solution {
    public int fib(int n) {
        if(n == 0)
            return 0;
        if(n == 1)
            return 1;
        return fib(n - 1) + fib( n -2);
    }
}
```

动态规划

```
class Solution {
    public int fib(int n) {
        int a = 0, b = 1, sum;
        for(int i = 0; i < n; i++){
            sum = (a + b) % 1000000007;
            a = b;
            b = sum;
        }
        return a;
    }
}


```
