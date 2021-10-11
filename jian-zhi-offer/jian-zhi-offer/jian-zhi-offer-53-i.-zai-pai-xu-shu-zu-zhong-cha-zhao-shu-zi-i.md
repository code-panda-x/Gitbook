# 剑指 Offer 53 - I. 在排序数组中查找数字 I

My ans: 无脑暴力解

```
class Solution {
    public int search(int[] nums, int target) {
        int res = 0;
        for(int i = 0; i < nums.length; i++)
        {
            if(nums[i] == target)
                res++;
        }
        return res;
    }
}
```

Binary Search:

![](<../../.gitbook/assets/image (8).png>)

```
class Solution {
    public int search(int[] nums, int target) {
        // 搜索右边界 right
        int i = 0, j = nums.length - 1;
        while(i <= j) {
            int m = (i + j) / 2;
            if(nums[m] <= target) i = m + 1;
            else j = m - 1;
        }
        int right = i;
        // 若数组中无 target ，则提前返回
        if(j >= 0 && nums[j] != target) return 0;
        // 搜索左边界 right
        i = 0; j = nums.length - 1;
        while(i <= j) {
            int m = (i + j) / 2;
            if(nums[m] < target) i = m + 1;
            else j = m - 1;
        }
        int left = j;
        return right - left - 1;
    }
}


```
