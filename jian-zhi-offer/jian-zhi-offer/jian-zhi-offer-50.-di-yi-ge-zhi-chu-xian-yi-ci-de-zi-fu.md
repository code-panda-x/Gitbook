# 剑指 Offer 50. 第一个只出现一次的字符

My ans: Hashmap

```
class Solution {
    public char firstUniqChar(String s) {
        HashMap<Character,Integer> mymap = new HashMap<Character,Integer>();
        if(s == null)
            return ' ';
        for(char c : s.toCharArray())
        {
            mymap.put(c,mymap.getOrDefault(c,0) + 1);
        }
        for(int i = 0; i < s.length(); i++)
        {
            if(mymap.get(s.charAt(i)) == 1)
                return s.charAt(i);
        }
        return ' ';
    }
}
```
