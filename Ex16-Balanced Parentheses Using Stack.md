# Ex16 Check for Balanced Parentheses Using Stack
## DATE:
## AIM:
To write a Java program that verifies whether the parentheses (brackets) in an input string are balanced — meaning each opening bracket (, {, [ has a corresponding and correctly ordered closing bracket ), }, ].

## Algorithm
1. Start
2. Read an input expression as a string
3. Create an empty stack
4. For each character in the string:
      a. If character is an opening bracket '(', '{', '[', push it onto the stack
      b. If character is a closing bracket ')', '}', ']':
            i. If the stack is empty, return false
            ii. Pop the top element from the stack
            iii. If the popped element does not match the type of closing bracket, return false
5. After processing all characters, if the stack is empty return true
6. If not empty return false
7. Display "Balanced" if true, otherwise "Not Balanced"
8. Stop


## Program:
```java
/*
Program to verify whether the parentheses (brackets) in an input string are balanced
Developed by: HARI PRIYA M
RegisterNumber: 212224240047  
*/

import java.util.*;

public class Node {

    public static boolean isBalanced(String str) {
        Stack<Character> stack = new Stack<>();

        for (char ch : str.toCharArray()) {
            if (ch == '(' || ch == '{' || ch == '[') {
                stack.push(ch);
            } else if (ch == ')' || ch == '}' || ch == ']') {
                if (stack.isEmpty()) return false;
                char top = stack.pop();
                if ((ch == ')' && top != '(') ||
                    (ch == '}' && top != '{') ||
                    (ch == ']' && top != '[')) {
                    return false;
                }
            }
        }
        return stack.isEmpty();
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter expression: ");
        String str = sc.nextLine();

        if (isBalanced(str))
            System.out.println("Balanced");
        else
            System.out.println("Not Balanced");

        sc.close();
    }
}

```

## Output:
<img width="499" height="234" alt="image" src="https://github.com/user-attachments/assets/b9992652-1b23-4943-bbc5-f0021056e32f" />



## Result:
Thus,the program correctly checks whether an input string has balanced parentheses using a stack.
