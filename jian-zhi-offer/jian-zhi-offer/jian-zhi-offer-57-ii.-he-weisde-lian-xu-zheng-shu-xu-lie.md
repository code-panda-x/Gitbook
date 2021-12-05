---
description: 看到连续，就应该想到滑动窗口
---

# 剑指 Offer 57 - II. 和为s的连续正数序列

滑动窗口的while判断条件当i大于target/2的时候后面都不用算了，两个大于等于target/2的数连续数相加肯定大于target，我是用的int n = target / 2; while(i <= n) 判断的。

```
public int[][] findContinuousSequence(int target) {
    int i = 1; // 滑动窗口的左边界
    int j = 1; // 滑动窗口的右边界
    int sum = 0; // 滑动窗口中数字的和
    List<int[]> res = new ArrayList<>();

    while (i <= target / 2) {
        if (sum < target) {
            // 右边界向右移动
            sum += j;
            j++;
        } else if (sum > target) {
            // 左边界向右移动
            sum -= i;
            i++;
        } else {
            // 记录结果
            int[] arr = new int[j-i];
            for (int k = i; k < j; k++) {
                arr[k-i] = k;
            }
            res.add(arr);
            // 左边界向右移动
            sum -= i;
            i++;
        }
    }

    return res.toArray(new int[res.size()][]);
}


```

