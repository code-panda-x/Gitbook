# 剑指 Offer 10- II. 青蛙跳台阶问题

```
class Solution {
    public int numWays(int n) {
        int a = 1, b = 1, sum;
        for(int i = 0; i < n; i++){
            sum = (a + b) % 1000000007;
            a = b;
            b = sum;
        }
        return a;
    }
}


```

魔改斐波那契数列

```
class Solution {
    public int numWays(int n) {
        if(n == 0)
            return 1;
        if(n <= 2)
            return n;

        int [] dp = new int [n+1];
        dp[1] = 1;
        dp[2] = 2;

        for(int i = 3; i <=n; i++){
            dp[i] = dp[i-1] + dp[i-2];
            dp[i] %= 1000000007;
        }
        return dp[n];
    }
}


```

