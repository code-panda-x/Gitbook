# 剑指 Offer 09. 用两个栈实现队列 LCOF

```
import java.util.*;
class CQueue {
        Stack<Integer> s1 = new Stack<Integer>();
        Stack<Integer> s2 = new Stack<Integer>();
    public CQueue() {

    }
    
    public void appendTail(int value) {
        s1.push(value);
    }
    
    public int deleteHead() {
        if (s2.isEmpty()) {
            while (!s1.isEmpty()) {
                s2.push(s1.pop());
            }
        } 
        if (s2.isEmpty()) {
            return -1;
        } else {
            int deleteItem = s2.pop();
            return deleteItem;
        }
    }
}

/**
 * Your CQueue object will be instantiated and called as such:
 * CQueue obj = new CQueue();
 * obj.appendTail(value);
 * int param_2 = obj.deleteHead();
 */
```
