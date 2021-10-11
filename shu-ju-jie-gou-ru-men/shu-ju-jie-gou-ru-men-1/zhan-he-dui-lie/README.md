# 栈和队列

妙啊

```
class Solution {
    public boolean isValid(String s) {

        Stack<Character> mystack = new Stack<>();
        boolean res = false;
        for(char c : s.toCharArray())
        {
            if(!mystack.isEmpty())
            {
                char t = mystack.peek();
                if(t == '(' && c == ')' || t == '[' && c == ']' || t == '{' && c == '}')
                {
                    mystack.pop();
                    continue;
                }
            }
            mystack.push(c);
        }
        return mystack.empty();
    }
}

```

思路清晰

```
public boolean isValid(String s) {
        Stack<Character> stack = new Stack<>();
        char[] charArray = s.toCharArray();

        for (char ch : charArray) {
            //如果是左括号则直接入栈
            if (ch == '(' || ch == '{' || ch == '[') {
                stack.push(ch);
            } else {
               //如果是右括号，并且此时栈不为空
                if (!stack.isEmpty()) {
                    if (ch == ')') {
                        if (stack.pop() != '(')
                            return false;
                    } else if (ch == '}') {
                        if (stack.pop() != '{')
                            return false;
                    } else {
                        if (stack.pop() != '[')
                            return false;
                    }
                }
                else{ //此时栈为空，但却来了个右括号，也直接返回false
                    return false;
                }
            }
        }
        return stack.isEmpty();
    }
```
