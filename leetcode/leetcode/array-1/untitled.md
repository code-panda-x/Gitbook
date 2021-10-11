---
description: 是真不会这个算法
---

# 26. Remove Duplicates from Sorted Array

Two pointers

```
class Solution {
    public int removeDuplicates(int[] nums) {
        int l = 0;
        int r = 1;
        while(r < nums.length)
        {
            if(nums[l] != nums[r])
            {
                l++;
                nums[l] = nums[r];
            }

            
            r++;
        }
        return l + 1;
    }
}
```
