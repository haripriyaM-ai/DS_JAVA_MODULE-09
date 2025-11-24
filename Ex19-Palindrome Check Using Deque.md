# Ex19 Palindrome Check Using Deque
## DATE:
## AIM:
To design a program that checks whether a given message is a palindrome by removing all non-alphanumeric characters, converting all characters to lowercase, and using a deque data structure for comparison.

## Algorithm
1. Start
2. Read the input message as a string
3. Create an empty deque of characters
4. Convert the string to lowercase and iterate through each character
5. Insert only alphanumeric characters into the deque
6. While deque size is greater than 1:
      a. Remove character from the front
      b. Remove character from the rear
      c. Compare the two, and if not equal return false
7. If all characters match, return true
8. Display whether the string is palindrome or not
9. Stop


## Program:
```java
/*
Program to checks whether a given message is a palindrome by removing all non-alphanumeric characters.
Developed by: HARI PRIYA M 
RegisterNumber: 212224240047 
*/

import java.util.*;

public class Node {

    public static boolean isPalindrome(String s) {
        Deque<Character> deque = new ArrayDeque<>();

        for (char ch : s.toLowerCase().toCharArray()) {
            if (Character.isLetterOrDigit(ch)) {
                deque.addLast(ch);
            }
        }

        while (deque.size() > 1) {
            if (deque.removeFirst() != deque.removeLast()) {
                return false;
            }
        }

        return true;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter message: ");
        String message = sc.nextLine();

        if (isPalindrome(message))
            System.out.println("Palindrome");
        else
            System.out.println("Not Palindrome");

        sc.close();
    }
}

```

## Output:
<img width="565" height="238" alt="image" src="https://github.com/user-attachments/assets/c66bb998-76b9-4e29-a35e-c5730a76871e" />



## Result:
The program successfully removes all non-alphanumeric characters, converts the text to lowercase, and uses a deque to efficiently compare characters from both ends. Hence, it determines whether the string is a palindrome.
