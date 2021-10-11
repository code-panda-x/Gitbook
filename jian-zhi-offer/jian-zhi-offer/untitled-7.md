# 剑指 Offer 21. 调整数组顺序使奇数位于偶数前面

头尾双指针

i：奇数就略过，往后找到第一个奇数

j: 偶数就略过，往前找第一个偶数

交换

```
class Solution {
    public int[] exchange(int[] nums) {
        int i = 0;
        int j = nums.length - 1;

        while(i < j)
        {
            while(nums[i] % 2 == 1 && i < j)
                i++;
            while(nums[j] % 2 == 0 && i < j)
                j--;

            int tmp = nums[i];
            nums[i] = nums[j];
            nums[j] = tmp;        
        }
        return nums;
    }
}
```

slow fast pointer

fast找奇数，找到了放到slow++, 没找到fast++继续找

```
class Solution {
    public int[] exchange(int[] nums) {
       int slow = 0;
       int fast = 0;

       while(fast < nums.length)
       {
           if(nums[fast] % 2 == 1)
           {
               int tmp = nums[fast];
               nums[fast] = nums[slow];
               nums[slow] = tmp;
               slow++;
           }
           
            fast++;
       }

       return nums;
    }
}
```
