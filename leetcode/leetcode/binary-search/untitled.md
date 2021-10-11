---
description: >-
  https://leetcode.com/explore/learn/card/binary-search/125/template-i/952/discuss/154836/The-INF-and-INF-method-but-with-a-better-explanation-for-dummies-like-me
---

# 33. Search in Rotated Sorted Array

Can't sort array because it requires original index

Revised BS:

```
public class Solution {
public int search(int[] A, int target) {
    int lo = 0;
    int hi = A.length - 1;
    while (lo < hi) {
        int mid = (lo + hi) / 2;
        if (A[mid] == target) return mid;
        
        if (A[lo] <= A[mid]) {
            if (target >= A[lo] && target < A[mid]) {
                hi = mid - 1;
            } else {
                lo = mid + 1;
            }
        } else {
            if (target > A[mid] && target <= A[hi]) {
                lo = mid + 1;
            } else {
                hi = mid - 1;
            }
        }
    }
    return A[lo] == target ? lo : -1;
}
```

INF -INF method

```
class Solution {
public:
    int search(vector<int>& nums, int target) 
    {
            int l = 0, r = nums.size()-1;
            while(l <= r)
            {
                int mid = (r - l)/2 + l;
                int comparator = nums[mid];
                // Checking if both target and nums[mid] are on same side.
                if((target < nums[0]) && (nums[mid] < nums[0]) || (target >= nums[0]) && (nums[mid] >= nums[0]))
                    comparator = nums[mid];
                else
                {
                    // Trying to figure out where nums[mid] is and making comparator as -INF or INF
                    if(target <nums[0])
                        comparator = -INFINITY;
                    else 
                        comparator = INFINITY;

                }
                if(target == comparator) return mid;
                if(target > comparator)            
                    l = mid+1;            
                else
                    r = mid-1;

            }
            return -1;
    }
};
```
