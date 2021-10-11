# 387. First Unique Character in a String

HashMap:

```
class Solution {
    public int firstUniqChar(String s) {
    HashMap<Character,Integer> mymap = new HashMap<>();
    for(char c : s.toCharArray())
        mymap.put(c,mymap.getOrDefault(c,0)+1);
    
    for(int i = 0; i < s.length(); i++)
    {
        if(mymap.get(s.charAt(i)) == 1)
            return i;
    }

    return -1;
    }
}
```
