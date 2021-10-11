# Matrix

\
​![](https://gblobscdn.gitbook.com/assets%2F-McA66JiQfbctw5GMDEE%2F-Mh3jPKn2ierI0RJbTXM%2F-Mh3wzLYeSYlGtLz0rpX%2Fimage.png?alt=media\&token=b3e602ee-2f89-4f0b-8837-d4b7eefe25a5)‌

Remember: Row ↓ Column →



二维数组 二维数组 转化

```
for (int x = 0; x < m * n; ++x) {
            ans[x / c][x % c] = nums[x / n][x % n];
        }
```

二维数组 一维数组 转化

```
for (int r = 0; r < R; ++r)
    for (int c = 0; c < C; ++c)
            int code = r * C + c;  // 转化为索引唯一的一维数组
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
