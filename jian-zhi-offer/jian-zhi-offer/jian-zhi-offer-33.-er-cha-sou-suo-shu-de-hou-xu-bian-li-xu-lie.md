---
description: 双指针+递归
---

# 剑指 Offer 33. 二叉搜索树的后序遍历序列

![](<../../.gitbook/assets/image (36).png>)

```
class Solution {
    public boolean verifyPostorder(int[] postorder) {
        return recur(postorder, 0, postorder.length - 1);
    }
    boolean recur(int[] postorder, int i, int j) {
    // 相当于指针遍历完了整个array
    // j为root的index
        if(i >= j) return true;
        int p = i;
        // 因为 左子树小于root
        while(postorder[p] < postorder[j]) p++;
        // 找到右子树开始的start index m
        int m = p;
        // 因为 右子树大于root
        // 找到右子树的end index p
        while(postorder[p] > postorder[j]) p++;
        
        return p == j && recur(postorder, i, m - 1) && recur(postorder, m, j - 1);
    }
}


```
