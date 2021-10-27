# 剑指 Offer 11. 旋转数组的最小数字

Binary Search:



```
class Solution {
    public int minArray(int[] numbers) {
        int i = 0, j = numbers.length - 1;
        while (i < j) {
            int m = (i + j) / 2;
            if (numbers[m] > numbers[j]) i = m + 1;    //因为 target必然比Number[j]小，numbers[m]大的话说明target不在在左边递增的array
            else if (numbers[m] < numbers[j]) j = m;  // mid 的右边一定不是最小数字，mid 有可能是，只要右边比中间大，那右边一定是有序数组 下一轮搜索区间是 [left, mid]
            else j--;
        }
        return numbers[i];
    }
}

```
