---
description: 我又懂了
---

# 剑指 Offer 60. n个骰子的点数

![](<../../.gitbook/assets/image (38).png>)

![](<../../.gitbook/assets/image (37).png>)

以两个筛子，3/36为例：分子为3意味着当前情况下形成点数和为4有三种可能的情况

&#x20;                          n1  n2

先前点数和为1： 1 + 3 = 4 --> 一种情况

先前点数和为2：2 + 2 = 4 --> 一种情况

先前点数和为3：3 + 1 = 4  -->  一种情况

一共三种情况，2个筛子，6^2，36种可能性

即：扔两个筛子，点数和为4所有可能出现的情况的概率



```
class Solution {
    public double[] dicesProbability(int n) {
        double[] dp = new double[6];
        Arrays.fill(dp, 1.0 / 6.0);
        for (int i = 2; i <= n; i++) {
            double[] tmp = new double[5 * i + 1];
            for (int j = 0; j < dp.length; j++) {
                for (int k = 0; k < 6; k++) {
                    tmp[j + k] += dp[j] / 6.0;
                }
            }
            dp = tmp;
        }
        return dp;
    }
}
```
