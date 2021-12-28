---
description: 回溯还是需要消化
---

# 剑指 Offer 38. 字符串的排列

```
class Solution {
    public String[] permutation(String s) {
        Set<String> list = new HashSet<>();
        char[] arr = s.toCharArray();
        StringBuilder sb = new StringBuilder();
        boolean[] visited = new boolean[arr.length];
        dfs(arr, "", visited, list);
        return list.toArray(new String[0]);
    }
    public void dfs(char[] arr, String s,  boolean[] visited, Set<String> list)
    {
        if(s.length() == arr.length)
        {
            list.add(s);
            return;
        }
        for(int i=0; i<arr.length; i++)
        {
            if(visited[i]) continue;
            visited[i] = true;
            dfs(arr, s+String.valueOf(arr[i]), visited, list);
            visited[i] = false;
        }

    }
}
```

能理解的模板

```
class Solution {
  private Set<String> ans;

  public String[] permutation(String s) {
    ans = new HashSet<>();
    backtrack(s.toCharArray(), new ArrayList<>());
    return ans.toArray(new String[0]);
  }

  private void backtrack(char[] chars, List<Integer> list) {
    if (list.size() == chars.length) {
      StringBuilder sb = new StringBuilder();
      // 拼接排列的字符串
      for (int i : list) sb.append(chars[i]);
      // 加入结果并去重
      ans.add(sb.toString());
    }
    for (int i = 0; i < chars.length; i++) {
      // 当前字符已经排列过，跳过
      if (list.contains(i)) continue;
      list.add(i);
      backtrack(chars, list);
      list.remove(list.size() - 1);
    }
  }
}

作者：huyii
链接：https://leetcode-cn.com/problems/zi-fu-chuan-de-pai-lie-lcof/solution/jian-zhi-offer-38-zi-fu-chuan-de-pai-lie-6f5q/
来源：力扣（LeetCode）
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。
```
