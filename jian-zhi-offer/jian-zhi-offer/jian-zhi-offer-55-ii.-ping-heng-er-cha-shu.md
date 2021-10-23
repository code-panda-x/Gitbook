# 剑指 Offer 55 - II. 平衡二叉树 1

```
class Solution {
    public boolean isBalanced(TreeNode root) {
        if (root == null) return true;
        
        if(Math.abs(depth(root.left) - depth(root.right)) <= 1 && isBalanced(root.left) && isBalanced(root.right))
            return true;
        return false;
    }

    private int depth(TreeNode root) {
        if (root == null) return 0;
        return Math.max(depth(root.left), depth(root.right)) + 1;
    }
}
```
