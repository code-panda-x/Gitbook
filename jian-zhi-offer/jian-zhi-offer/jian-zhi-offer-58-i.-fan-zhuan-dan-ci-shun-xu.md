---
description: 关于String 的用法
---

# 剑指 Offer 58 - I. 翻转单词顺序

```
    public String reverseWords(String s) {
        String[] splited = s.trim().split("\\s+");

        int i = 0;
        int j = splited.length - 1;

        while(i < j)
        {
            String tmp = splited[i];
            splited[i] = splited[j];
            splited[j] = tmp;
            i++;
            j--;
        }
        return String.join(" ",splited);
    }
}

time,space: O N
```
