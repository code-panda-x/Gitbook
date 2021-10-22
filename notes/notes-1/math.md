# Math

Math

**Math.abs()** returns the absolute value of a given argument.

#### Math.max(1,2);  Returns the highest value



求数位和

```
int sums(int x)
    int s = 0;
    while(x != 0) {
        s += x % 10;
        x = x / 10;
    }
    return s;

```



Round up

K / 2 + K % 2&#x20;

eg 3 / 2 + 3 % 2 = 2

### 关于取模

关于取模有什么说的呢？大家只需要记住一个公式即可：

`(x * y ) % z ==> ((x % z) * (y % z)) % z`

知道这个公式，当两个较大的数做乘法时，我们先求余再相乘，可以有效避免溢出。



正整数 pp​​ 值永远小于等于完全平方数的一半 (num / 2)（ p 为 1 除外）



**快速幂**（**Exponentiation by squaring**，平方求幂）分治思想

![](<../../.gitbook/assets/image (20).png>)

```
public int quickPow(int x, int y) {
    if (y == 0) {
        return 1;
    }
    int ret = quickPow(x, y / 2);
    return y % 2 == 0 ? ret * ret : ret * ret * x;
}


```



循环求余



```java
// (x^a) % p —— 循环求余法。固定搭配建议背诵
   public long  remainder(int x,int a,int p){  //x为底数，a为幂，p为要取的模
        long rem = 1 ;
        for (int i = 0; i < a; i++) {
            rem = (rem * x) % p ;   
        }
        return rem;
    }
```

\


```
# 求 (x^a) % p —— 快速幂求余
def remainder(x, a, p):
    rem = 1
    while a > 0:
        if a % 2: rem = (rem * x) % p
        x = x ** 2 % p
        a //= 2
    return rem

、
```

因为2\*2=1\*4，2\*3>1\*5, 所以将数字拆成2和3，能得到的积最大
