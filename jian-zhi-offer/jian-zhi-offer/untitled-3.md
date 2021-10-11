---
description: >-
  https://leetcode-cn.com/problems/shu-de-zi-jie-gou-lcof/solution/mian-shi-ti-26-shu-de-zi-jie-gou-xian-xu-bian-li-p/
---

# 剑指 Offer 26. 树的子结构

容易理解的递归：

```
class Solution {
    public boolean isSubStructure(TreeNode A, TreeNode B) {
        if(A== null || B==null){
            return false;
        }
        boolean r1 = recur(A,B);
        boolean r2 = isSubStructure(A.left,B);
        boolean r3 = isSubStructure(A.right,B);
        return r1||r2||r3;
    }

    public boolean recur(TreeNode A, TreeNode B){
        if(B== null){
            return true;
        }
        if(A==null|| A.val != B.val){
            return false;
        }
        return recur(A.left,B.left) && recur(A.right,B.right);
    }

}
```

简洁版

```
class Solution {
    public boolean isSubStructure(TreeNode A, TreeNode B) {
        return (A != null && B != null) && (recur(A, B) || isSubStructure(A.left, B) || isSubStructure(A.right, B));
    }
    boolean recur(TreeNode A, TreeNode B) {
        if(B == null) return true;
        if(A == null || A.val != B.val) return false;
        return recur(A.left, B.left) && recur(A.right, B.right);
    }
}


```
