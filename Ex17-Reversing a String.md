# Ex17 Reversing a String Using Stack Data Structure
## DATE:
## AIM:
To write a Java program that reverses an input string using a stack, without using built-in reverse functions.

## Algorithm
1. Start
2. Read the input string
3. Create an empty stack of characters
4. Push each character of the string onto the stack
5. Initialize an empty string reversed
6. Pop characters from the stack one by one and append them to reversed
7. Display the reversed string
8. Stop

## Program:
```java
/*
Program to reverses an input string using a stack
Developed by: HARI PRIYA M 
RegisterNumber: 212224240047 
*/

import java.util.*;

public class Node {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter a string: ");
        String str = sc.nextLine();

        Stack<Character> stack = new Stack<>();

        for (char ch : str.toCharArray()) {
            stack.push(ch);
        }

        String reversed = "";
        while (!stack.isEmpty()) {
            reversed += stack.pop();
        }

        System.out.println("Reversed string: " + reversed);

        sc.close();
    }
}

```

## Output:
<img width="409" height="223" alt="image" src="https://github.com/user-attachments/assets/eae6a234-fc3b-4efc-9bde-2029f52a6764" />



## Result:
Thus, the program successfully reverses the given string using a stack without relying on built-in reverse functions.
