# 剑指 Offer 40. 最小的k个数 1

1.排序

```
class Solution {
    public int[] getLeastNumbers(int[] arr, int k) {
        Arrays.sort(arr);
        int []res = new int [arr.length];
        res = Arrays.copyOfRange(arr, 0, k);
        return res;
    }
}
```

2\. Max heap

```
class Solution {
    public int[] getLeastNumbers(int[] arr, int k) {

        if(k == 0 || arr.length == 0)
            return new int[]{};
        PriorityQueue<Integer> heap = new PriorityQueue<>((x ,y) -> (y - x));
        
        for(int x : arr)
        {
            if(heap.size() < k)
                heap.offer(x);
            else if(x < heap.peek())
            {  
                heap.poll();
                heap.offer(x);
            }
        }

        int i = 0;
        int [] res = new int [heap.size()];
        for(int x : heap)
            res[i++] = x;

        return res;
    }
}
```
