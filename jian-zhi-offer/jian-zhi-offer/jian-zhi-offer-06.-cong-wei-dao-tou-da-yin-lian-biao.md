# 剑指 Offer 06. 从尾到头打印链表

MY ans

```
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
class Solution {
    public int[] reversePrint(ListNode head) {
        ListNode cur = head;
        List<Integer> arr = new ArrayList<>();
        int [] empty = new int [0];
        int size = 0;

        if(head == null)
            return empty;
        
        while(cur != null)
        {
            arr.add(cur.val);
            cur = cur.next;
            size++;
            
        }
        int [] res = new int[arr.size()];
        int j = 0;
        for(int num = arr.size()-1; num >= 0; num--)
            res[j++] = arr.get(num);

        return res;
    }
}
```



stack



recursion
