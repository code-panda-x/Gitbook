---
description: copyofrange其实是复制从 0 至 index-1个elements     （arr, inclusive, exclusive）
---

# 剑指 Offer 07. 重建二叉树

![](<../../.gitbook/assets/image (35).png>)

```
class Solution {
    public TreeNode buildTree(int[] preorder, int[] inorder) {
        //重建一开始是真的有点绕啊，但是其实理清了也还好，无非就是通过每次传进去的两个数组来构建新的二叉树
        //三部曲试一下吧
        //首先是啥时候结束
        //当传入的数组长度为0的时候就该结束了
        int length = preorder.length;
        if(length == 0 ) return null;
        //接下来是我们应该返回什么，那当然就是返回重建子树的根节点咯
        //每一层应该做些什么呢？
        //应该通过传进来的两个数组，根据他们之间的关系，来构建子树，并把新的参数传递下去
        //那么现在传进来了两个数组，一个是前序遍历的数组，那么首位必定是根节点，先拿下
        int rootValue = preorder[0];
        //有了数组的根节点以后我们自然需要的是左右子树，根据中序遍历的特点，只要找到了根节点，那么他两边自然
        //就是他的左右子树了
        //那么先在中序遍历的数组中找到根节点,并把它的坐标保存起来
        int rootIndex = 0;      
        for(int i = 0; i < length; i++){
            if(inorder[i] == rootValue){
                rootIndex = i;
                break;
            }
        }
        //至此我们已经找到了根和左右子树，那么设置一下根节点的左右节点，自然就是递归后返回的左右子树的根节点
        //先把我们的根节点创建出来
        TreeNode root = new TreeNode(rootValue);
        root.left = buildTree(Arrays.copyOfRange(preorder,1,rootIndex + 1),Arrays.copyOfRange(inorder,0,rootIndex));
        root.right = buildTree(Arrays.copyOfRange(preorder,1+rootIndex,length),Arrays.copyOfRange(inorder,rootIndex+1,length));
        //至于传入的数组如何分割可以自己通过测试用例来分析，这里不赘述了
        //至此节点创建，左右节点的设置均已完成，返回root
        return root;
        
    }

}  
```
