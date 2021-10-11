---
description: return new int[]{1,2};    int [] res = new int []{0,0};
---

# 167. Two Sum II - Input array is sorted

双指针

```
class Solution {
    public int[] twoSum(int[] numbers, int target) {
        int l = 0;
        int r = numbers.length - 1;
        int [] res = new int []{0,0};
        for(int i = 0; i < numbers.length; i++)
        {
            if(numbers[l] + numbers[r] == target)
                return new int[] {l+1,r+1};
            else if(numbers[l] + numbers[r] < target)
                l++;
            else
                r--;
        }
        return res;
    }
}
```

Hashset 找 target - num

```
class Solution {
    public int[] twoSum(int[] numbers, int target) {
        HashMap<Integer,Integer> myMap= new HashMap<Integer,Integer>(); 
    
        for(int i = 0; i < numbers.length; i++)
        {
            myMap.put(numbers[i],i); 
        }
        
        for(int i = 0; i < numbers.length; i++)
        {
            if (myMap.containsKey(target - numbers[i]))
                return new int[]{i+1,myMap.get(target-numbers[i])+1};
        }
        return null;
    }
}
```
