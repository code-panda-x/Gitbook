# 剑指 Offer 64. 求1+2+…+n 1

recur

```
class Solution {
    public int sumNums(int n) {
        if(n <= 1)
            return 1;
        return n + sumNums(n-1);
    }
}
```

Use &&

```
class Solution {
    int res = 0;
    public int sumNums(int n) {
        boolean x = n > 1 && sumNums(n - 1) > 0;
        res += n;
        return res;
    }
}

```
