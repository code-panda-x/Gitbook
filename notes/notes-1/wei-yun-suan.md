# 位运算

<< 左移：增大  2的指数

\>> 右移：删除右边的

转化为位运算： 

向下整除 n/2 等价于 右移一位 n >> 1 

取余数 n%2 等价于 判断二进制最右位 n&1 ；



技巧总结

n & (n-1) 把最低位的1变成0

n & 1 returns last digit

y & 1 != 0   y为奇数

y & 1 == 0  y为偶数



1 << 3

```
00000001 << 3 == 00001000
```

In other words, `1 << 3 == 8`, since you shift the 1 bit over by 3 places.



Operator table



```
----------------------------------------------------------------------------------------
Operator   Description                                   Example
----------------------------------------------------------------------------------------
|=        bitwise inclusive OR and assignment operator   C |= 2 is same as C = C | 2
^=        bitwise exclusive OR and assignment operator   C ^= 2 is same as C = C ^ 2
&=        Bitwise AND assignment operator                C &= 2 is same as C = C & 2
<<=       Left shift AND assignment operator             C <<= 2 is same as C = C << 2
>>=       Right shift AND assignment operator            C >>= 2 is same as C = C >> 2  
----------------------------------------------------------------------------------------
```

Java supports two types of right shift operators. The **>>** operator is a signed right shift operator and **>>>** is an unsigned right shift operator. The left operands value is moved right by the number of bits specified by the right operand

![](<../../.gitbook/assets/image (19).png>)





![](<../../.gitbook/assets/image (17).png>)

![](<../../.gitbook/assets/image (18).png>)
