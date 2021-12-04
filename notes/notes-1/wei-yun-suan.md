# 位运算

移动：

1 << 3  左移：增大  2的指数

```
00000001 << 3 == 00001000
```

In other words, `1 << 3 == 8`, since you shift the 1 bit over by 3 places.



">>>"无符号右移

操作规则：无论正负数，前面补零。

">>"右移 --> n >> = 1

操作规则：正数前面补零，负数前面补1

"<<"左移 --> n <<= 1

操作规则：无论正负数，后面补零。



eg

```
n >>>= 1; 减小
```



转化为位运算：&#x20;

向下整除 n/2 等价于 右移一位 n >>= 1  （删除右边的最后一位）

取余数 n%2 等价于  n&1  （判断二进制最右位是否为1）



无进位/有进位求和：

^ 异或 ----相当于 无进位的求和， 想象10进制下的模拟情况：（如:19+1=20；无进位求和就是10，而非20；因为它不管进位情况）

& 与 ----相当于求每位的进位数， 先看定义：1&1=1；1&0=0；0&0=0；即都为1的时候才为1，正好可以模拟进位数的情况,还是想象10进制下模拟情况：（9+1=10，如果是用&的思路来处理，则9+1得到的进位数为1，而不是10，所以要用<<1向左再移动一位，这样就变为10了）；



技巧总结

**n & (n-1) 把最低位的1变成0 --> count 1's, check power of 2**

n & 1 returns last digit

y & 1 != 0   y为奇数

y & 1 == 0  y为偶数



* 交换律
* 结合律（即(a^b)^c == a^(b^c)）
* 对于任何数x，都有x^x=0，x^0=x
* 自反性 A XOR B XOR B = A xor 0 = A ---> A XOR B = C 则 C XOR B = A



XOR

![](<../../.gitbook/assets/image (35) (1).png>)

相同的数异或为0，不同的异或为1。0和任何数异或等于这个数本身。

Z = X ^ Y



Java 里面 ^ 指的是xor

\| 指的是or

[https://blog.csdn.net/vebasan/article/details/6193916](https://blog.csdn.net/vebasan/article/details/6193916)

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
