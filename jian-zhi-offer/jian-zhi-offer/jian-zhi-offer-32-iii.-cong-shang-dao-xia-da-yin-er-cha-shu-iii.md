# 剑指 Offer 32 - III. 从上到下打印二叉树 III

1. 用res.size判断奇偶，用add的时候根据奇偶reverse

```
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode(int x) { val = x; }
 * }
 */
class Solution {
    public List<List<Integer>> levelOrder(TreeNode root) {
        List<List<Integer>> res = new ArrayList<>();
        Queue<TreeNode> myq = new LinkedList<TreeNode>();

        if(root == null)
            return res;
        myq.add(root);
        while(!myq.isEmpty())
        {
            List<Integer> row = new ArrayList<>();
            int size = myq.size();

            for(int i = 0; i < size; i++)
            {
                TreeNode node = myq.poll();
                row.add(node.val);
                if(node.left != null)
                    myq.add(node.left);
                if(node.right != null)
                    myq.add(node.right); 
            }
            if(res.size() % 2 != 0)
                Collections.reverse(row);
            res.add(row);
        }

        return res;
    }
}
```

2\. 利用res.size 判断奇偶，用LinkedList根据奇偶插入

LinkedList tmp = new LinkedList<>();

tmp.addLast(node.val); // 偶数层 -> 队列头部&#x20;

&#x20;tmp.addFirst(node.val);



3\. 用flag判断奇偶

