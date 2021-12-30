---
description: 一般来说BT的complexity都是O(N)
---

# BST

[https://leetcode-cn.com/problems/binary-tree-preorder-traversal/solution/leetcodesuan-fa-xiu-lian-dong-hua-yan-shi-xbian-2/](https://leetcode-cn.com/problems/binary-tree-preorder-traversal/solution/leetcodesuan-fa-xiu-lian-dong-hua-yan-shi-xbian-2/)

![](<../../.gitbook/assets/image (36) (1) (1).png>)



中序遍历和后续遍历的特性 首先来看题目给出的两个已知条件 中序遍历序列 和 后序遍历序列 根据这两种遍历的特性我们可以得出两个结论

在后序遍历序列中,最后一个元素为树的根节点 在中序遍历序列中,根节点的左边为左子树，根节点的右边为右子树



BST的inorder traversal得出的即是 sorted array



{% embed url="https://blog.csdn.net/My_Jobs/article/details/43451187" %}



A `binary search tree` (BST), a special form of a binary tree, satisfies the binary search property:

1. The value in each node must be `greater than` (or equal to) any values stored in its left subtree.
2. The value in each node must be `less than` (or equal to) any values stored in its right subtree.



二叉搜索树的中序遍历的序列是递增排序的序列。中序遍历的遍历次序：Left -> Node -> Right。&#x20;



Successor 代表的是中序遍历序列的下一个节点。即比当前节点大的最小节点，简称后继节点。 先取当前节点的右节点，然后一直取该节点的左节点，直到左节点为空，则最后指向的节点为后继节点。&#x20;



&#x20;Predecessor 代表的是中序遍历序列的前一个节点。即比当前节点小的最大节点，简称前驱节点。先取当前节点的左节点，然后取该节点的右节点，直到右节点为空，则最后指向的节点为前驱节点。&#x20;

![](<../../.gitbook/assets/image (24).png>)

{% embed url="https://leetcode-cn.com/problems/delete-node-in-a-bst/solution/shan-chu-er-cha-sou-suo-shu-zhong-de-jie-dian-by-l/" %}





DFS: 用stack

前序遍历：根结点 ---> 左子树 ---> 右子树

中序遍历：左子树---> 根结点 ---> 右子树

后序遍历：左子树 ---> 右子树 ---> 根结点

BFS: 用Queue

层次遍历

**所谓广度优先搜索，就是从起点出发，每次都尝试访问同一层的节点，如果同一层都访问完了，再访问下一层，最后广度优先搜索找到的路径就是从起点开始的最短合法路径**。



A **height-balanced** binary tree is a binary tree in which the depth of the two subtrees of every node never differs by more than one.



