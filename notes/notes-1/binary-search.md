# Binary Search



If have no idea how to compare, have an example and try compare mid to start/end and try to shrink to the right direction

* 排序数组中的搜索问题，首先想到 **二分法** 解决。

What do I compare to when there's no target?

Possible solutions:

1. Mid and Start or End
2. Mid and mid+1



一般来说 r= len-  1，若是没有用到nums\[r]可以用 r = len

Binary Search is generally composed of 3 main sections:

1. _**Pre-processing**_ - Sort if collection is unsorted.
2. _**Binary Search**_ - Using a loop or recursion to divide search space in half after each comparison.
3. _**Post-processing**_ - Determine viable candidates in the remaining space.

Template1:

* Initial Condition: `left = 0, right = length-1`
* Termination: `left > right`
* Searching Left: `right = mid-1`
* Searching Right: `left = mid+1`

```
int binarySearch(int[] nums, int target){
  if(nums == null || nums.length == 0)
    return -1;

  int left = 0, right = nums.length - 1;
  while(left <= right){
    // Prevent (left + right) overflow
    int mid = left + (right - left) / 2;
    if(nums[mid] == target){ return mid; }
    else if(nums[mid] < target) { left = mid + 1; }
    else { right = mid - 1; }
  }

  // End Condition: left > right
  return -1;
}


```

Template2:



* Initial Condition: `left = 0, right = length`
* Termination: `left == right`
* Searching Left: `right = mid`
* Searching Right: `left = mid+1`

```
int binarySearch(int[] nums, int target){
  if(nums == null || nums.length == 0)
    return -1;

  int left = 0, right = nums.length;
  while(left < right){
    // Prevent (left + right) overflow
    int mid = left + (right - left) / 2;
    if(nums[mid] == target){ return mid; }
    else if(nums[mid] < target) { left = mid + 1; }
    else { right = mid; }
  }

  // Post-processing:
  // End Condition: left == right
  if(left != nums.length && nums[left] == target) return left;
  return -1;
}
```

You use `while (start <= end)` if you are returning the match from inside the loop.

You use `while (start < end)` if you want to exit out of the loop first, and then use the result of `start` or `end` to return the match.



Template 3



* Initial Condition: `left = 0, right = length-1`
* Termination: `left + 1 == right`
* Searching Left: `right = mid`
* Searching Right: `left = mid`

```
int binarySearch(int[] nums, int target) {
    if (nums == null || nums.length == 0)
        return -1;

    int left = 0, right = nums.length - 1;
    while (left + 1 < right){
        // Prevent (left + right) overflow
        int mid = left + (right - left) / 2;
        if (nums[mid] == target) {
            return mid;
        } else if (nums[mid] < target) {
            left = mid;
        } else {
            right = mid;
        }
    }

    // Post-processing:
    // End Condition: left + 1 == right
    if(nums[left] == target) return left;
    if(nums[right] == target) return right;
    return -1;
}
```

![](<../../.gitbook/assets/image (10).png>)

一般都是 left <= right， mid + 1 mid - 1

记住：

(l <= r) --> mid + 1 - 1

(l < r) --> r = mid
