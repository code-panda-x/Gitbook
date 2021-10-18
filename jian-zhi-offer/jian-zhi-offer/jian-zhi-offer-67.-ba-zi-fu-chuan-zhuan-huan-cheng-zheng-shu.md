---
description: 有点麻烦
---

# 剑指 Offer 67. 把字符串转换成整数

```
class Solution {
 public int strToInt(String str) {
        char[] ch = str.trim().toCharArray();
        if(ch.length==0) return 0;
        //用于判断正负号，正数（包括前面无符号）1，复数-1；
        int sign = 1;
        //默认有符号，即准备第二个char开始循环。
        int index = 1;
        if(ch[0]=='-') sign = -1;
        //当不是负号也不是正号时，从第一个char开始循环。
        else if(ch[0]!='+') index =0;
        //long型结果是为了使结果超出时能进行判断
        long res = 0;

        while(index < ch.length){
            //当遇到不是数字时退出循环，即使是“+”，“-”，“+-2”这样的数也能返回0；
            if(ch[index]<'0'||ch[index]>'9') break;
            //结果不断往上加
            res = res*10 +ch[index]-'0';
            //加完立马判断是否出借，这里res肯定是正数（sign位单独拿出来了），所以只与MAX比
            if(res>Integer.MAX_VALUE) return sign==1?Integer.MAX_VALUE:Integer.MIN_VALUE;
            index++;
        }

        //返回符号与结果的乘机（int和long不能相乘）
        return sign*(int)res;
    }
}
```
