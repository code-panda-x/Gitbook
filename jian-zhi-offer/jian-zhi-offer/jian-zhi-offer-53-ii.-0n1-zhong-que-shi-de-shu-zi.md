# 剑指 Offer 53 - II. 0～n-1中缺失的数字

当判断条件和target相等时，i即是答案



```
if(nums[m] <= target) i = m + 1;
if(nums[m] == target) i = m + 1;
```

```
class Solution {
    public int missingNumber(int[] nums) {
        int i = 0, j = nums.length - 1;
        while(i <= j) {
            int m = (i + j) / 2;
            if(nums[m] == m) i = m + 1;
            else j = m - 1;
        }
        return i;
    }
}


```
