# 232. Implement Queue using Stacks

精髓在于 peek，总是先把stack2排空了再把stac1 的value push进去

push就正常push，唯一不同的就在于pop

```
class MyQueue {
        Stack<Integer> stack1 = new Stack<>();
        Stack<Integer> stack2 = new Stack<>();
    public MyQueue() {

    }
    
    public void push(int x) {
        stack1.push(x);
            
    }
    
    public int pop() {
        peek();
        return stack2.pop();
    }
    
    public int peek() {
        if(stack2.isEmpty())
        {
            while(!stack1.isEmpty())
                stack2.push(stack1.pop());
        }
        
        return stack2.peek();
    }
    
    public boolean empty() {
        return stack1.isEmpty() && stack2.isEmpty();
    }
}
```
