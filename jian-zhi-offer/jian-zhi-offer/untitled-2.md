# 剑指 Offer 32 - II. 从上到下打印二叉树 II

为什么不能用：

`for(int i = 0; i < q.size(); i++)`

q.size()会随每一次q.poll()而减少，所以不行

也可以用： for(int i = q.size() ; i > 0; i--)



size代表每一层node个数，size不会超过2，因为每次只有iteration到了两个if判断才会更新size大小

当到达最后一个node，左右两边都为null，while(Queue.isEmpty)就结束了





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
        if(root == null)
            return new ArrayList<>();

        List<List<Integer>> result = new ArrayList<>();
        
        Queue<TreeNode> queue = new LinkedList<>();
        queue.add(root);

        while(queue.size() != 0)
        {
            List<Integer> res = new ArrayList<>();
            int size = queue.size();

            for(int i = size; i > 0; i--)
            {
                TreeNode temp = queue.poll();
                res.add(temp.val);

                if(temp.left != null)
                    queue.add(temp.left);
                if(temp.right != null)
                    queue.add(temp.right);

            }
            result.add(res);
        }


        return result;
    }
}
```
