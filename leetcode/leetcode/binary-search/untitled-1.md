---
description: 边界问题，如果没有target可以选择和start 或者 end比
---

# 153. Find Minimum in Rotated Sorted Array

和start 比

```
class Solution {
    public int findMin(int[] num) {
       int start=0,end=num.length-1;
        
        while (start<end) {
            if (num[start]<num[end]) // 妙啊
                return num[start];
            
            int mid = (start+end)/2;
            
            if (num[mid]>=num[start]) {
                start = mid+1;
            } else {
                end = mid;
            }
        }
        
        return num[start];
        
    }
}
```

和 end 比

```
class Solution {
    public int findMin(int[] nums) {
        int l = 0;
        int r = nums.length - 1;
        
        while(l < r)
        {
            int mid = l + (r-l)/2;
            
            if(nums[mid] > nums[r]) 
                l = mid + 1;
            else   
                r = mid;    
        }
        return nums[l];
    }
}

class Solution {
    public int findMin(int[] nums) {
        int low = 0;
        int high = nums.length - 1;
        while (low < high) {
            int pivot = low + (high - low) / 2;
            if (nums[pivot] < nums[high]) { // 说明当前是在第二个数组，最小值在左边，往左找
                high = pivot;
            } else { // 说明当前是在第一个升序的数组，且此数组的所有值都大于high，所以继续往右边找
                low = pivot + 1;
            }
        }
        return nums[low];
    }
}


```



`r= length - 1 是因为用到了nums[r]`
