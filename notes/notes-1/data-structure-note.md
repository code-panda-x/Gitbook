# data structure note

2D Array

**1. C++ stores the two-dimensional array as a one-dimensional array.**

The picture below shows the actual structure of a M \* N array A:![](https://s3-lc-upload.s3.amazonaws.com/uploads/2018/03/31/screen-shot-2018-03-31-at-161748.png)

So actually A\[i]\[j] equals to A\[i \* N + j] if we defined _A_ as a one-dimensional array which also contains M \* N elements.

**2. In Java, the two-dimensional array is actually a one-dimensional array which contains M elements, each of which is an array of N integers.**

The picture below shows the actual structure of a two-dimensional array A in Java:

![](https://s3-lc-upload.s3.amazonaws.com/uploads/2018/03/31/screen-shot-2018-03-31-at-162857.png)

![](../../.gitbook/assets/image.png)

Remember: Row ↓   Column  → 



**String**:

C++: mutable, can use == to compare

Java: immutable, can not use == to compare, Use .equals()



Common uses:

mystring.charAt(5) returns char at the position 5

'6' - '0' Converts a char to an int



To concatenate string in Java:

1. Convert to char \[]
2. Use StringBuilder 

