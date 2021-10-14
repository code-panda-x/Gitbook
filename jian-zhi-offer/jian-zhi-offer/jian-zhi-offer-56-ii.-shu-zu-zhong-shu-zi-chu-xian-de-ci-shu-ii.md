# 剑指 Offer 56 - II. 数组中数字出现的次数 II

HashMap, 位运算实在不太会

```
class Solution {
    public int singleNumber(int[] nums) {
        HashMap<Integer, Integer> map = new HashMap<>();
        for(int i = 0; i < nums.length; i++)
        {
            int val = map.getOrDefault(nums[i],0);
            map.put(nums[i],val+1);
        }

        for(Integer x : map.keySet())
        {
            if(map.get(x) == 1)
                return x;
        }
        return -1;
    }
}
```
