# 剑指 Offer 04. 二维数组中的查找

My ans:暴力解

```
class Solution {
    public boolean findNumberIn2DArray(int[][] matrix, int target) {
        if (matrix == null || matrix.length == 0 || matrix[0].length == 0) 
            return false;
        int m = matrix.length;
        int n = matrix[0].length;
      
        for(int i = 0; i < m; i++)
        {
            for(int j = 0; j < n;j++)
            {
                if(matrix[i][j] == target)
                    return true;
            }
        }
        return false;
    }
}
```

因为是有序的，可以从右上角开始找

```
class Solution {
    public boolean findNumberIn2DArray(int[][] matrix, int target) {
        if (matrix == null || matrix.length == 0 || matrix[0].length == 0) {
            return false;
        }
        int rows = matrix.length, columns = matrix[0].length;
        int row = 0, column = columns - 1;
        while (row < rows && column >= 0) {
            int num = matrix[row][column];
            if (num == target) {
                return true;
            } else if (num > target) {
                column--;
            } else {
                row++;
            }
        }
        return false;
    }
}


```
