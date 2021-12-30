# DP

{% embed url="https://leetcode.com/problems/target-sum/discuss/455024/DP-IS-EASY!-5-Steps-to-Think-Through-DP-Questions." %}

1. Category&#x20;
2. States 哪些variable是在不停更新变化的？
3. Decisions  下一步该怎么走？怎么做决定？
4. Base cases  什么时候结束？



为什么 dp = new int \[n + 1]

因为无论如何dp 数组都是从0开始，如果需要遍历每个数即： i <= n，最后返回最后一个数return dp\[n] 需要一个额外的位置留给dp\[0]。如果不initialize n+1，i遍历到n-1就没有位置了，最后一个数n会大于dp size

eg

```
class Solution {
    public int numWays(int n) {
        if(n == 0)
            return 1;
        if(n <= 2)
            return n;

        int [] dp = new int [n+1];
        dp[1] = 1;
        dp[2] = 2;

        for(int i = 3; i <=n; i++){
            dp[i] = dp[i-1] + dp[i-2];
            dp[i] %= 1000000007;
        }
        return dp[n];
    }
}

idx 0 1 2 3 4 5
dp. 0.1 2 3.5 8


class Solution {
    public int maxSubArray(int[] A) {   
       int [] dp = new int [A.length];
        dp[0] = A[0];
        int max = dp[0];
        
        for(int i = 1; i < A.length; i++){
            dp[i] = Math.max(A[i], A[i] + dp[i-1]);
            max = Math.max(max, dp[i]);
        }
        return max;
    }
}
```
