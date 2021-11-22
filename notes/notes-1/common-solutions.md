# array



Use two pointers (Usually Operate backwards From right to left!)

Use one pointer and rewrite the array in place&#x20;

If can't come up with in place, create a new array



Two pointers：Normally, if want to use two pointer, the array is sorted



当需要求array的一半 = 另一半，应该想到找sum / 2

在if里面 &&的两个statement 顺序matters！，例子如下，如果颠倒顺序，无法通过

```
    public boolean validMountainArray(int[] A) {
        int n = A.length, i = 0, j = n - 1;
        while (i + 1 < n && A[i] < A[i + 1]) i++;
        while (j > 0 && A[j - 1] > A[j]) j--;
        return i > 0 && i == j && j < n - 1;
```



compare array 前后值可以这样：

Arrays.sort : O(N lg N)

```
 Arrays.sort(nums);
        for(int ind = 1; ind < nums.length; ind++) {
            if(nums[ind] == nums[ind - 1]) {
                return true;
            }
        }
```

找中间值



```
int mid = (newlen -1) / 2;
        
        return newlen % 2 == 0? (double)(merged[mid] + merged[mid+1]) /2 : merged[mid];
```

Reverse array

```
 while (i < j) {
      char t = a[i];
      a[i++] = a[j];
      a[j--] = t;
    }
```



Find number of digits of an int:

```
while(num != 0) { nums /= 10; count++; }
```



往前 shift:&#x20;

```
for (int j; j < length; j++) {
   nums[j] = nums[j+1];
}

// deletion
length--;
```

往后 shift:

```
for(int j = arr.length - 2; j > i; j--)
    arr[j+1] = arr[j];
```

****

**Array: **

Counting sort**：**Count the frequency hence sort the array



桶分组：

[https://leetcode-cn.com/problems/contains-duplicate-iii/solution/c-li-yong-tong-fen-zu-xiang-xi-jie-shi-b-ofj6/](https://leetcode-cn.com/problems/contains-duplicate-iii/solution/c-li-yong-tong-fen-zu-xiang-xi-jie-shi-b-ofj6/)&#x20;

