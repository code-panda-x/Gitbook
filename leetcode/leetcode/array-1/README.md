# Array

Use two pointers (Usually Operate backwards From right to left!)

Use one pointer and rewrite the array in place 

If can't come up with in place, create a new array



重塑matrix

```
for (int x = 0; x < m * n; ++x) {
            ans[x / c][x % c] = nums[x / n][x % n];
        }


```
