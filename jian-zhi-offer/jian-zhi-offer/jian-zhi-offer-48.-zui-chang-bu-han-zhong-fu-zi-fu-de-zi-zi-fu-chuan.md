---
description: 仍需理解DP
---

# 剑指 Offer 48. 最长不含重复字符的子字符串

HashSet 取巧：

```
class Solution {
    public int lengthOfLongestSubstring(String s) {
        HashSet <Character> myset = new HashSet<>();

        int i = 0;
        int j = 0;
        int max = 0;

        while(i < s.length())
        {
            if(!myset.contains(s.charAt(i)))
            {
                myset.add(s.charAt(i++));
                max = Math.max(myset.size(),max);
            }
            else
            {
                myset.remove(s.charAt(j++));
            }
        }

        return max;
    }
}
```
