# 3. Longest Substring Without Repeating Characters

滑动窗口

之所以j++在if里是因为else remove了第一个重复的element，size--，下一次循环才把重复的element 加入set, 此时才达到最大length。

```
class Solution {
    public int lengthOfLongestSubstring(String s) {
        HashSet<Character> myset = new HashSet<>();
        int i = 0;
        int j = 0;
        int max = 0;

        while(j < s.length())
        {
            if(!myset.contains(s.charAt(j)))
            {
                myset.add(s.charAt(j++));
                max = Math.max(max,myset.size());
            }
            else
                myset.remove(s.charAt(i++));
                
            
           
        }
        return max;
    }
}
```
