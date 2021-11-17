# 剑指 Offer 42. 连续子数组的最大和

贪心：如果之前的和<0 则舍弃，> 0则相加

```
class Solution {
    public int maxSubArray(int[] nums) {
        int sum = 0;
        int ans = nums[0];
        if(nums.length == 1)
            return ans;

        for(int i = 0; i < nums.length; i++)
        {
   
            if(sum > 0)
                sum+=nums[i];
            else
                sum = nums[i];

            ans = Math.max(ans,sum);

                
        }
        return ans;
    }
}


```

DP

```
class Solution {
    public int maxSubArray(int[] nums) {
        int pre = 0, maxAns = nums[0];
        for (int x : nums) {
        // 注意这里是pre+x 和 x，可以理解成一种贪心思想，如果加上pre小于当前，那就舍弃pre
            pre = Math.max(pre + x, x);
            maxAns = Math.max(maxAns, pre);
        }
        return maxAns;
    }
}
-
```

```
int maxSubArray3(std::vector<int> &nums) {
    assert(!nums.empty());

    int n = nums.size();
    int maxSum = nums[0];

    // 如果当前值小于0，
    // 重新开始(全局最大值更新)
    for (int i = 1; i < n; i++) {
        // 更新当前的最大值
        if (nums[i - 1] > 0) {
            nums[i] += nums[i - 1];
        }
        // 更新全局的最大值
        maxSum = std::max(nums[i], maxSum);
    }

    return maxSum;
}


```
