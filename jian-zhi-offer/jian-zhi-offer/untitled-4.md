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
        if(n <= 1)
            return n;

        int [] dp = new int [n+1];
        dp[0] = 0;
        dp[1] = 1;

        for(int i = 2; i <=n; i++){
            dp[i] = dp[i-1] + dp[i-2];
            dp[i] %= 1000000007;
        }
        return dp[n];
    }
}
```

优化：

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
