# Matrix

\
​‌

![](https://gblobscdn.gitbook.com/assets%2F-McA66JiQfbctw5GMDEE%2F-Mh3jPKn2ierI0RJbTXM%2F-Mh3wzLYeSYlGtLz0rpX%2Fimage.png?alt=media\&token=b3e602ee-2f89-4f0b-8837-d4b7eefe25a5)

Remember: Row ↓ Column →



1d --> 2d

```
int array2d[][] = new int[10][3];


for(int i=0; i<10;i++)
   for(int j=0;j<3;j++)
       array2d[i][j] = array1d[(j*10) + i]; 
```

2d --> 1d

```
for (int r = 0; r < R; ++r)
    for (int c = 0; c < C; ++c)
            int code = r * C + c;  // 转化为索引唯一的一维数组
```

Reshape to any dimensions: 566

```
res[x / c][x % c] = mat[i][j];
```



重塑matrix

```
for (int x = 0; x < m * n; ++x) {
            ans[x / c][x % c] = nums[x / n][x % n];
        }


```

九宫格

```
int box_index = (i / 3 ) * 3 + j / 3;

 int regionRow = 3 * (row / 3);  //region start row
    int regionCol = 3 * (col / 3);    //region start col
    for (int i = 0; i < 9; i++) {
        if (board[i][col] == c) return false; //check row
        if (board[row][i] == c) return false; //check column
        if (board[regionRow + i / 3][regionCol + i % 3] == c) return false; //check 3*3 block
    }
```

![](<../../.gitbook/assets/image (6).png>)

Matrix Transpose: Basically row becomes col, col becomes row

![](<../../.gitbook/assets/image (40) (1) (1) (1).png>)

```
for (int i = 0; i < matrix.length; i++) {
    for (int j = 0; j < i; j++) {
        int temp = matrix[i][j];
        matrix[i][j] = matrix[j][i];
        matrix[j][i] = temp;
    }
}
```



Matrix Rotate: Most of the time dealing with transpose

可以反推，拿到题先从target matrix入手，取transpose。拿其和original matrix做比较，进行操作

[https://leetcode.com/problems/rotate-image/discuss/18872/A-common-method-to-rotate-the-image](https://leetcode.com/problems/rotate-image/discuss/18872/A-common-method-to-rotate-the-image)



reverse所有column

```
while(l < r){
    int temp[] = matrix[l];
    matrix[l] = matrix[r];
    matrix[r] = temp;
    l++;
    r--;
}
```



判断Diagonal Anti-diagonal

```
if (row == col)
{
    diagonal += toAdd;
}

if (col == (cols.length - row - 1))
{
    antiDiagonal += toAdd;
}
```

