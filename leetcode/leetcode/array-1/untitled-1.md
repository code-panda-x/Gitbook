---
description: 没想到可以直接2*i来判断，并且可以一次循环就结束
---

# 1346. Check If N and Its Double Exist

 奇数情况（\*2） + 偶数情况 （/2）

```
public boolean checkIfExist(int[] arr) {
        Set<Integer> seen = new HashSet<>();   
        for (int i : arr) {
            if (seen.contains(2 * i) || i % 2 == 0 && seen.contains(i / 2))
                return true;
            seen.add(i);
        }
        return false;
    }

Time, space : O N
```
