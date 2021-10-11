# 剑指 Offer 57. 和为s的两个数字

因为是有序数组，可以双指针

```
class Solution {
    public int[] twoSum(int[] nums, int target) {
        int i = 0, j = nums.length - 1;
        while(i < j) {
            int s = nums[i] + nums[j];
            if(s < target) i++;
            else if(s > target) j--;
            else return new int[] { nums[i], nums[j] };
        }
        return new int[0];
    }
}

Time: O n
Space: O 1
```

Hashset

```
class Solution {
    public int[] twoSum(int[] nums, int target) {
        HashSet <Integer> myset = new HashSet<>();

        for(int i = 0; i < nums.length; i++)
        {
            if(myset.contains(target - nums[i]))
                return new int []{target - nums[i], nums[i]};
            else
                myset.add(nums[i]);
        }
        return new int [] {0,0};
    }
}

Time: On
Space: On
```
