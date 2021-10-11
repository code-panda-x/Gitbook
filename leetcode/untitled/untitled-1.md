# 4. Median of Two Sorted Arrays

合并后找出中间值，注意找中间值的方法（奇偶）

```
class Solution {
    public double findMedianSortedArrays(int[] nums1, int[] nums2) {
        int len1 = nums1.length;
        int len2 = nums2.length;
        int newlen = len1 + len2;
        int [] merged = new int [newlen];
        int index = 0;
        int i = 0;
        int j = 0;
        
        while(i < len1 && j < len2)
        {
            if(nums1[i] <= nums2[j])
                merged[index++] = nums1[i++];
            else
                merged[index++] = nums2[j++];
        }

        while(i < len1)
            merged[index++] = nums1[i++];
        while(j < len2)
            merged[index++] = nums2[j++];
        
        int mid = (newlen -1) / 2;
        
        return newlen % 2 == 0? (double)(merged[mid] + merged[mid+1]) /2 : merged[mid];
        
    }
}
```
