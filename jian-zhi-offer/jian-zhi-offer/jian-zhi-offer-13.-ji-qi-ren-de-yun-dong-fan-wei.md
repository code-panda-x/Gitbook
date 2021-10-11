---
description: 怎样才能自己写出来？
---

# 剑指 Offer 13. 机器人的运动范围

只需要往右下移动

```
class Solution {

    public int movingCount(int m, int n, int k) {
        boolean[][] visited = new boolean[m][n];
        return dfs(visited, m, n, k, 0, 0);
    }

    private int dfs(boolean[][] visited, int m, int n, int k, int i, int j) {
        if(i >= m || j >= n || visited[i][j] || bitSum(i) + bitSum(j) > k) return 0;
        visited[i][j] = true;
        return 1 + dfs(visited, m, n, k, i + 1, j) + dfs(visited, m, n, k, i, j + 1) ;
    }

    private int bitSum(int n) {
        int sum = 0;
        while(n > 0) {
            sum += n % 10;
            n /= 10; 
        }
        return sum;
    }
}
```
