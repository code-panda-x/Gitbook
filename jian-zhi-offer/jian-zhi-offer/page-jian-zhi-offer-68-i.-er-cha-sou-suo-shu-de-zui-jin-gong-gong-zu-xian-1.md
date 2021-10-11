# Page剑指 Offer 68 - I. 二叉搜索树的最近公共祖先1

```
class Solution {
    public TreeNode lowestCommonAncestor(TreeNode root, TreeNode p, TreeNode q) {
        if(root.val < p.val && root.val < q.val)
            return lowestCommonAncestor(root.right,p,q);
        if(root.val > p.val && root.val > q.val)
            return lowestCommonAncestor(root.left,p,q);

    
        return root;

    }
}
```
