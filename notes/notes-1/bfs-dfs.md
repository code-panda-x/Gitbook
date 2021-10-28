# BFS DFS

{% embed url="https://leetcode-cn.com/problems/binary-tree-level-order-traversal/solution/bfs-de-shi-yong-chang-jing-zong-jie-ceng-xu-bian-l/" %}



DFS,BFS 惯用trick，向四个方向update index：

```
int[] dx = new int[] {-1, 1, 0, 0};
        int[] dy = new int[] {0, 0, -1, 1};
        while (!queue.isEmpty()) {
            int[] point = queue.poll();
            int x = point[0], y = point[1];
            for (int i = 0; i < 4; i++) {
                int newX = x + dx[i];
                int newY = y + dy[i];
               
                if (newX >= 0 && newX < m && newY >= 0 && newY < n 
                        && matrix[newX][newY] == -1) {
                    matrix[newX][newY] = matrix[x][y] + 1;
                    
                    queue.offer(new int[] {newX, newY});
                }
            }
            
1. trick：一个1d数组搞定 int[] DIR = new int[]{0, 1, 0, -1, 0};   lc:542
     int[] curr = q.poll();
    int r = curr[0], c = curr[1];
    for (int i = 0; i < 4; ++i) {
        int nr = r + DIR[i], nc = c + DIR[i+1];
     
2. 一个2d数组搞定        
    cell = queue.poll();
    int[][] dirs = {{-1, 0}, {1, 0}, {0, -1}, {0, 1}};. int[] 
    int i = cell[0], j = cell[1];
    for (int d = 0; d < 4; ++d) {
        int ni = i + dirs[d][0];
        int nj = j + dirs[d][1];

3. 两个1d数组        
    int[] rowOffsets = {0, 1, 0, -1};
    int[] colOffsets = {1, 0, -1, 0};
    for (int d = 0; d < 4; ++d) {
      ret = this.backtrack(row + rowOffsets[d], col + colOffsets[d], word, index + 1);
      if (ret)
        break;
    }

```

DFS&#x20;

template1

```
/*
 * Return true if there is a path from cur to target.
 */
boolean DFS(Node cur, Node target, Set<Node> visited) {
    return true if cur is target;
    for (next : each neighbor of cur) {
        if (next is not in visited) {
            add next to visted;
            return true if DFS(next, target, visited) == true;
        }
    }
    return false;
}
```

template2

```
/*
 * Return true if there is a path from cur to target.
 */
boolean DFS(int root, int target) {
    Set<Node> visited;
    Stack<Node> stack;
    add root to stack;
    while (s is not empty) {
        Node cur = the top element in stack;
        remove the cur from the stack;
        return true if cur is target;
        for (Node next : the neighbors of cur) {
            if (next is not in visited) {
                add next to visited;
                add next to stack;
            }
        }
    }
    return false;
}
```



BFS

template

```
如果不需要确定当前遍历到了哪一层，BFS 模板如下。

while queue 不空：
    cur = queue.pop()
    for 节点 in cur的所有相邻节点：
        if 该节点有效且未访问过：
            queue.push(该节点)


如果要确定当前遍历到了哪一层，BFS 模板如下。
这里增加了 level 表示当前遍历到二叉树中的哪一层了，也可以理解为在一个图中，现在已经走了多少步了。size 表示在当前遍历层有多少个元素，也就是队列中的元素数，我们把这些元素一次性遍历完，即把当前层的所有元素都向外走了一步。

level = 0
while queue 不空：
    size = queue.size()
    while (size --) {
        cur = queue.pop()
        for 节点 in cur的所有相邻节点：
            if 该节点有效且未被访问过：
                queue.push(该节点)
    }
    level ++;


```
