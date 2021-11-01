# Backtrack

Template

```
def backtrack(candidate):
    if find_solution(candidate):
        output(candidate)
        return
    
    # iterate all possible candidates.
    for next_candidate in list_of_candidates:
        if is_valid(next_candidate):
            # try this partial candidate solution
            place(next_candidate)
            # given the candidate, explore further.
            backtrack(next_candidate)
            # backtrack
            remove(next_candidate)
```

Common problems and solutions

{% embed url="https://leetcode.com/problems/permutations/discuss/18239/A-general-approach-to-backtracking-questions-in-Java-(Subsets-Permutations-Combination-Sum-Palindrome-Partioning)" %}

In a permutation order matters, so the permutation (1 2 3) is not the same as (2 1 3).&#x20;

In a combination order does not matter so the combination (2 3) is the same as (3 2).

![](<../../.gitbook/assets/image (39) (2).png>)



Combination: 77

combination/subsets 总是要在for里update i，因为如果不update，下一次backtrack从0开始，会加入当前数字前出现的数字。因为combination不在乎order，这样是不行的。根据题意，加入当前重复的element也是可以的，见 39

如何update i：

i + 1 表示不能用重复的element

i 表示可以用重复的element





Permutation: 46

**permutation是不需要start的**
