---
description: 绝啦
---

# 剑指 Offer 29. 顺时针打印矩阵

```
class Solution {
    public int[] spiralOrder(int[][] matrix) {
        if(matrix.length == 0)
            return new int[]{};
        int b = matrix.length - 1;
        int r = matrix[0].length - 1;
        int l = 0;
        int t = 0;
        int idx = 0;
        int [] res = new int [(b+1) * (r+1)];
        while(true)
        {
            for(int i = l; i <= r; i++)
                res[idx++] = matrix[t][i];
            if(++t > b)
                break;
            for(int i = t; i <= b; i++)
                res[idx++] = matrix[i][r];
            if(l > --r)
                break;
            for(int i = r; i >= l; i--)
                res[idx++] = matrix[b][i];
            if(t > --b)
                break;
            for(int i = b; i >= t; i--)
                res[idx++] = matrix[i][l];
            if(++l > r)
                break;
            
        }
        return res;
    }
}
```
