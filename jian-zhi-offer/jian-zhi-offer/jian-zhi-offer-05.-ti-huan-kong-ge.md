# 剑指 Offer 05. 替换空格

My ans:

```
class Solution {
    public String replaceSpace(String s) {
        int space = 0;
        for(int i = 0; i < s.length(); i++)
        {
            if(s.charAt(i) == ' ')
                space++;
        }

        char [] arr = new char [s.length() + space * 2];
        int j = 0;
        for(int i = 0; i < s.length(); i++)
        {
            if(s.charAt(i) == ' ')
            {
                arr[j] = '%';
                arr[++j] = '2';
                arr[++j] = '0';
            }
            else
                arr[j] = s.charAt(i);
            j++;
        }

        String res = String.valueOf(arr);
        return res;
    }
}
```

String builder

```
class Solution {
    public String replaceSpace(String s) {
        StringBuilder res = new StringBuilder();
        for(Character c : s.toCharArray())
        {
            if(c == ' ') res.append("%20");
            else res.append(c);
        }
        return res.toString();
    }
}


```

Replace

```
机灵鬼用的是s.replace(" ","%20");
```
