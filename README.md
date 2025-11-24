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

# Ex18 Simulation of a Ticket Counter Using Queue (Linked List Implementation)
## DATE:
## AIM:
To simulate the functioning of a ticket counter that operates on a First-In-First-Out (FIFO) basis using a queue implemented via a linked list in Java.
## Algorithm
1. Start
2. Create a queue using linked list with front and rear pointers
3. Read number of customers n
4. Enqueue n customer ticket numbers into the queue
5. Dequeue elements one by one and display them in serving order
6. Continue until queue becomes empty
7. Stop
 

## Program:
```java
/*
Program to functioning of a ticket counter that operates on a First-In-First-Out (FIFO)
Developed by: HARI PRIYA M 
RegisterNumber: 212224240047 
*/

import java.util.*;

public class Node {

    static class ListNode {
        int data;
        ListNode next;

        ListNode(int data) {
            this.data = data;
            this.next = null;
        }
    }

    static class QueueLL {
        ListNode front, rear;

        QueueLL() {
            front = rear = null;
        }

        void enqueue(int data) {
            ListNode newNode = new ListNode(data);
            if (rear == null) {
                front = rear = newNode;
                return;
            }
            rear.next = newNode;
            rear = newNode;
        }

        int dequeue() {
            if (front == null)
                return -1;
            int val = front.data;
            front = front.next;
            if (front == null)
                rear = null;
            return val;
        }

        boolean isEmpty() {
            return front == null;
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        QueueLL queue = new QueueLL();

        System.out.print("Enter number of customers: ");
        int n = sc.nextInt();

        System.out.println("Enter customer ticket numbers:");
        for (int i = 0; i < n; i++) {
            queue.enqueue(sc.nextInt());
        }

        System.out.println("Serving order:");
        while (!queue.isEmpty()) {
            System.out.print(queue.dequeue() + " ");
        }

        sc.close();
    }
}

```

## Output:
<img width="470" height="271" alt="image" src="https://github.com/user-attachments/assets/ea52ee3d-3362-4518-8df0-737c18f4eb45" />



## Result:
Thus, the program successfully simulates a ticket counter queue where customers are served in FIFO order using a linked list-based queue implementation.# Ex18 Simulation of a Ticket Counter Using Queue (Linked List Implementation)
## DATE:
## AIM:
To simulate the functioning of a ticket counter that operates on a First-In-First-Out (FIFO) basis using a queue implemented via a linked list in Java.
## Algorithm
1. Start
2. Create a queue using linked list with front and rear pointers
3. Read number of customers n
4. Enqueue n customer ticket numbers into the queue
5. Dequeue elements one by one and display them in serving order
6. Continue until queue becomes empty
7. Stop
 

## Program:
```java
/*
Program to functioning of a ticket counter that operates on a First-In-First-Out (FIFO)
Developed by: HARI PRIYA M 
RegisterNumber: 212224240047 
*/

import java.util.*;

public class Node {

    static class ListNode {
        int data;
        ListNode next;

        ListNode(int data) {
            this.data = data;
            this.next = null;
        }
    }

    static class QueueLL {
        ListNode front, rear;

        QueueLL() {
            front = rear = null;
        }

        void enqueue(int data) {
            ListNode newNode = new ListNode(data);
            if (rear == null) {
                front = rear = newNode;
                return;
            }
            rear.next = newNode;
            rear = newNode;
        }

        int dequeue() {
            if (front == null)
                return -1;
            int val = front.data;
            front = front.next;
            if (front == null)
                rear = null;
            return val;
        }

        boolean isEmpty() {
            return front == null;
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        QueueLL queue = new QueueLL();

        System.out.print("Enter number of customers: ");
        int n = sc.nextInt();

        System.out.println("Enter customer ticket numbers:");
        for (int i = 0; i < n; i++) {
            queue.enqueue(sc.nextInt());
        }

        System.out.println("Serving order:");
        while (!queue.isEmpty()) {
            System.out.print(queue.dequeue() + " ");
        }

        sc.close();
    }
}

```

## Output:
<img width="470" height="271" alt="image" src="https://github.com/user-attachments/assets/ea52ee3d-3362-4518-8df0-737c18f4eb45" />



## Result:
Thus, the program successfully simulates a ticket counter queue where customers are served in FIFO order using a linked list-based queue implementation.
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
The program successfully removes all non-alphanumeric characters, converts the text to lowercase, and uses a deque to efficiently compare characters from both ends. Hence, it determines whether the string is a palindrome.# Ex19 Palindrome Check Using Deque
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
# Ex20 Sorting an Array using Merge Sort Algorithm
## DATE:
## AIM:
To design a program that sorts a given array of integers in ascending order without using built-in sorting functions, achieving O(n log n) time complexity and minimal space usage.
## Algorithm
1. Start
2. Read total number of elements n
3. Create an integer array arr of size n and input values
4. Call mergeSort(arr, 0, n-1)
5. In mergeSort(arr, left, right):
      a. If left < right:
           i. Find mid = (left + right) / 2
           ii. Recursively call mergeSort on left half
           iii. Recursively call mergeSort on right half
           iv. Call merge(arr, left, mid, right)
6. In merge(arr, left, mid, right):
      a. Copy left half and right half into temporary arrays
      b. Merge both halves in ascending order back into arr
      c. Copy remaining elements if any
7. Display the sorted array
8. Stop
   

## Program:
```java
/*
Program tosorts a given array of integers in ascending order without using built-in sorting functions
Developed by: HARI PRIYA M 
RegisterNumber: 212224240047 
*/

import java.util.*;

public class Node {

    public static void merge(int[] arr, int left, int mid, int right) {
        int n1 = mid - left + 1;
        int n2 = right - mid;

        int[] L = new int[n1];
        int[] R = new int[n2];

        for (int i = 0; i < n1; i++)
            L[i] = arr[left + i];
        for (int j = 0; j < n2; j++)
            R[j] = arr[mid + 1 + j];

        int i = 0, j = 0, k = left;

        while (i < n1 && j < n2) {
            if (L[i] <= R[j]) {
                arr[k] = L[i];
                i++;
            } else {
                arr[k] = R[j];
                j++;
            }
            k++;
        }

        while (i < n1) {
            arr[k] = L[i];
            i++;
            k++;
        }

        while (j < n2) {
            arr[k] = R[j];
            j++;
            k++;
        }
    }

    public static void mergeSort(int[] arr, int left, int right) {
        if (left < right) {
            int mid = (left + right) / 2;
            mergeSort(arr, left, mid);
            mergeSort(arr, mid + 1, right);
            merge(arr, left, mid, right);
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter number of elements: ");
        int n = sc.nextInt();

        int[] arr = new int[n];
        System.out.println("Enter array elements:");
        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
        }

        mergeSort(arr, 0, n - 1);

        System.out.println("Sorted array:");
        for (int num : arr) {
            System.out.print(num + " ");
        }

        sc.close();
    }
}

```

## Output:
<img width="427" height="270" alt="image" src="https://github.com/user-attachments/assets/df336eda-ab87-4957-88cb-b923016cf7e6" />



## Result:
The program has been successfully implemented and executed.
It sorts the given array of integers in ascending order using the Merge Sort algorithm with a time complexity of O(n log n) and minimal extra space.
