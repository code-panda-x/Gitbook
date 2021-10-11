---
description: >-
  https://leetcode-cn.com/problems/binary-tree-preorder-traversal/solution/leetcodesuan-fa-xiu-lian-dong-hua-yan-shi-xbian-2/
---

# BST

中序遍历和后续遍历的特性 首先来看题目给出的两个已知条件 中序遍历序列 和 后序遍历序列 根据这两种遍历的特性我们可以得出两个结论

在后序遍历序列中,最后一个元素为树的根节点 在中序遍历序列中,根节点的左边为左子树，根节点的右边为右子树



{% embed url="https://blog.csdn.net/My_Jobs/article/details/43451187" %}

DFS: 用stack

前序遍历：根结点 ---> 左子树 ---> 右子树

中序遍历：左子树---> 根结点 ---> 右子树

后序遍历：左子树 ---> 右子树 ---> 根结点

BFS: 用Queue

层次遍历

**所谓广度优先搜索，就是从起点出发，每次都尝试访问同一层的节点，如果同一层都访问完了，再访问下一层，最后广度优先搜索找到的路径就是从起点开始的最短合法路径**。







```
```
