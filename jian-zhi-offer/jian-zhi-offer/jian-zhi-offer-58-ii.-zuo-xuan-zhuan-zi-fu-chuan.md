# 剑指 Offer 58 - II. 左旋转字符串

MY ans: 试出来的边界

```
class Solution {
    public String reverseLeftWords(String s, int n) {
        char [] res = new char [s.length()];
        n = n % s.length();
        String myres = null;

        if(s == null)
            return null;
        for(int i = 0; i < n; i++)
        {
            res[s.length() - n + i] = s.charAt(i);
        }

        for(int i = 0; i < s.length() - n; i++)
        {
            res[i] = s.charAt(i+n);
        }

        myres = String.valueOf(res);
        return myres;
    }
}
```



Reverse 
