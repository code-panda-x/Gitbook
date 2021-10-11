---
description: 没想到
---

# 136. Single Number

Xor

Let's say we have an array - \[2,1,4,5,2,4,1].\
What we are doing is essentially this-

\=> 0 ^ 2 ^ 1 ^ 4 ^ 5 ^ 2 ^ 4 ^ 1

\=> 0^ 2^2 ^ 1^1 ^ 4^4 ^5 (Rearranging, taking same numbers together)

\=> 0 ^ 0 ^ 0 ^ 0 ^ 5

\=> 0 ^ 5

\=> 5 :)

![](<../../../.gitbook/assets/image (27).png>)

```
class Solution {
    public int singleNumber(int[] nums) {
        int result = 0;
    for (int i = 0; i<nums.length; i++)
    {
		result ^=nums[i];
    }
	return result;
    }
}
```
