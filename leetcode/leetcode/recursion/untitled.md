---
description: 待搞懂
---

# 489. Robot Room Cleaner

So in the given backtracking function, the `d` means the direction that the robot is currently facing. As mentioned in the post, 0 means the robot is facing up, 1 means right, 2 means down, and 3 means left. `i` keeps track of how many right turns we've made so far. So, each time you make a right turn, you will increase `i` by 1.\
Assume the robot is currently facing left, so `d` is 3, and you want it to try all the directions in the following clockwise sequence: 3(left), 0(up), 1(right), 2(down).\
As you can see, since the starting direction is 3(facing left), when you add 1(turn right once), the answer becomes 4. However, the correct answer should be 0(up), since now the robot is facing up. That's why we introduce the modulo operation here, it is used to make sure that the direction always falls into the range of `0, 1, 2, 3`.



```
class Solution {
  // going clockwise : 0: 'up', 1: 'right', 2: 'down', 3: 'left'
  int[][] directions = {{-1, 0}, {0, 1}, {1, 0}, {0, -1}};
  Set<Pair<Integer, Integer>> visited = new HashSet();
  Robot robot;

  public void goBack() {
    robot.turnRight();
    robot.turnRight();
    robot.move();
    robot.turnRight();
    robot.turnRight();
  }

  public void backtrack(int row, int col, int d) {
    visited.add(new Pair(row, col));
    robot.clean();
    // going clockwise : 0: 'up', 1: 'right', 2: 'down', 3: 'left'
    for (int i = 0; i < 4; ++i) {
      int newD = (d + i) % 4;
      int newRow = row + directions[newD][0];
      int newCol = col + directions[newD][1];

      if (!visited.contains(new Pair(newRow, newCol)) && robot.move()) {
        backtrack(newRow, newCol, newD);
        goBack();
      }
      // turn the robot following chosen direction : clockwise
      robot.turnRight();
    }
  }

  public void cleanRoom(Robot robot) {
    this.robot = robot;
    backtrack(0, 0, 0);
  }
}
```
