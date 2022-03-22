# Page 1

因为要留top frequency，所以必须要用minHeap sort frequency

因为output要frequency从大到小排列，所以要reverse output，因为minHeap挨个poll出来的是从小到大的顺序

因为同frequency的需要从小到大的lex排列，同时output reverse了，所以用maxHeap挨个poll出最大的，剩下的就是相对lex小的。output里的是maxheap 挨个poll出来都是大的，因为reverse了，放到最后，在最前面的是小的。最后得到从小到大的排列。

```
class Solution {
    public List<String> topKFrequent(String[] words, int k) {
        
        List<String> result = new LinkedList<>();
        Map<String, Integer> map = new HashMap<>();
        for(int i=0; i<words.length; i++)
        {
            if(map.containsKey(words[i]))
                map.put(words[i], map.get(words[i])+1);
            else
                map.put(words[i], 1);
        }
        // getvalue minheap  get key maxheap
        PriorityQueue<Map.Entry<String, Integer>> pq = new PriorityQueue<>(
                 (a,b) -> a.getValue()==b.getValue() ? b.getKey().compareTo(a.getKey()) : a.getValue()-b.getValue()
        );
        
        for(Map.Entry<String, Integer> entry: map.entrySet())
        {
            pq.offer(entry);
            if(pq.size()>k)
                pq.poll();
        }
// 0 is to reverse output, add at index 0
        while(!pq.isEmpty())
            result.add(0, pq.poll().getKey());
        
        return result;
    }
}
```
