# 剑指 Offer 16. 数值的整数次方

基本理解快速幂：利用递归 让指数n不断/2，直到0. 回溯的时候根据指数n的奇偶判断相乘x几次

```
class Solution {
    public double myPow(double x, int n) {
        return n >= 0 ? recur(x,n) : 1 / recur(x,n);
    }

    public double recur(double x, int n)
    {
        if(n == 0)
            return 1;

        double y = recur(x, n/2);
        return n % 2 == 0 ? y * y : y * y * x;
    }
}
```

位运算
