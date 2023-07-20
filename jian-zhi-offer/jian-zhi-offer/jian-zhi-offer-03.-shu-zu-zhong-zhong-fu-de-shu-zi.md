# 剑指 Offer 03. 数组中重复的数字

My ans: Hashset

```
class Solution {
    public int findRepeatNumber(int[] nums) {
        HashSet<Integer> myset = new HashSet<>();
        for(int num : nums)
        {
            if(!myset.add(num))
                return num;
        }
        return 0;
    }
}
```

原地交换，index映射

![](<../../.gitbook/assets/image (7) (1).png>)

```
class Solution {
    public int findRepeatNumber(int[] nums) {
        HashSet<Integer> myset = new HashSet<>();
        for(int num : nums)
        {
            if(!myset.add(num))
                return num;
        }
        return 0;
    }
}
```
