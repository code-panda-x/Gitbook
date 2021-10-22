# 剑指 Offer 17. 打印从1到最大的n位数

```
class Solution {
    public int[] printNumbers(int n) {
        double target = Math.pow(10,n);
        int i = 0;
        int [] res = new int [(int)target - 1];
        while(i < (double)target - 1)
            res[i++] = i;

        return res;
    }
}
```
