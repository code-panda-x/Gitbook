---
description: 好像懂了，需要理解循环求余和快速幂求余
---

# 剑指 Offer 14- II. 剪绳子 II

![](<../../.gitbook/assets/image (39) (1).png>)

3越多乘积越大

```
class Solution {
    public int cuttingRope(int n) {
        if(n == 2)
            return 1;
        if(n == 3)
            return 2;
        long res = 1;
        while(n > 4){
            res *= 3;
            res = res % 1000000007;
            n -= 3;
        }
        return (int)(res * n % 1000000007);
    }
}
```
