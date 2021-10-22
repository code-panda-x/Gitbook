# Binary Search Tree



A `binary search tree` (BST), a special form of a binary tree, satisfies the binary search property:

1. The value in each node must be `greater than` (or equal to) any values stored in its left subtree.
2. The value in each node must be `less than` (or equal to) any values stored in its right subtree.



二叉搜索树的中序遍历的序列是递增排序的序列。中序遍历的遍历次序：Left -> Node -> Right。&#x20;



Successor 代表的是中序遍历序列的下一个节点。即比当前节点大的最小节点，简称后继节点。 先取当前节点的右节点，然后一直取该节点的左节点，直到左节点为空，则最后指向的节点为后继节点。&#x20;



&#x20;Predecessor 代表的是中序遍历序列的前一个节点。即比当前节点小的最大节点，简称前驱节点。先取当前节点的左节点，然后取该节点的右节点，直到右节点为空，则最后指向的节点为前驱节点。&#x20;

![](<../../../.gitbook/assets/image (24).png>)

{% embed url="https://leetcode-cn.com/problems/delete-node-in-a-bst/solution/shan-chu-er-cha-sou-suo-shu-zhong-de-jie-dian-by-l/" %}



