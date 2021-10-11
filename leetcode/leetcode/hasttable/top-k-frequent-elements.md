---
description: >-
  https://leetcode.com/problems/top-k-frequent-elements/discuss/81635/3-Java-Solution-using-Array-MaxHeap-TreeMap
---

# 347. Top K Frequent Elements

Bucketsort : [https://www.youtube.com/watch?v=YPTqKIgVk-k](https://www.youtube.com/watch?v=YPTqKIgVk-k)

```
class Solution {
    public int[] topKFrequent(int[] nums, int k) {
       Map<Integer, Integer> map = new HashMap<>();
        for(int n: nums){
            map.put(n, map.getOrDefault(n,0)+1);
        }
        
        // corner case: if there is only one number in nums, we need the bucket has index 1.
        List<Integer>[] bucket = new List[nums.length+1];
        for(int n:map.keySet()){
            int freq = map.get(n);
            if(bucket[freq]==null)
                bucket[freq] = new LinkedList<>();
            bucket[freq].add(n);
        }
        
        List<Integer> res = new LinkedList<>();
        for(int i=bucket.length-1; i>0 && k>0; --i){
            if(bucket[i]!=null){
                List<Integer> list = bucket[i]; 
                res.addAll(list);
                k-= list.size();
            }
        }
        
        int[] array = new int[res.size()];
        for (int i = 0; i < res.size(); i++) {
         array[i] = res.get(i); // Watch out for NullPointerExceptions!
        }
        return array;
    }
}
```

Also: Max heap, tree map
