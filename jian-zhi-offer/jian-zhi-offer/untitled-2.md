# 剑指 Offer 32 - II. 从上到下打印二叉树 II

为什么不能用：

`for(int i = 0; i < q.size(); i++)`

q.size()会随每一次q.poll()而减少，所以不行

也可以用： for(int i = q.size() ; i > 0; i--)



size代表每一层node个数，size不会超过2，因为每次只有iteration到了两个if判断才会更新size大小

当到达最后一个node，左右两边都为null，while(Queue.isEmpty)就结束了









*   ```
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
            Queue<TreeNode> queue = new LinkedList<>();
            List<List<Integer>> res = new ArrayList<>();
            if(root != null) queue.add(root);
            while(!queue.isEmpty()) {
                List<Integer> tmp = new ArrayList<>();
                int size = queue.size();
                for(int i = 0;i < size; i++) {
                    TreeNode node = queue.poll();
                    tmp.add(node.val);
                    if(node.left != null) queue.add(node.left);
                    if(node.right != null) queue.add(node.right);
                }
                res.add(tmp);
            }
            return res;
        }
    }


    ```

    &#x20;}

    }
