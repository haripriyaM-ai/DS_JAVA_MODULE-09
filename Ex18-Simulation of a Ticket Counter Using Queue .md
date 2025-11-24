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
Thus, the program successfully simulates a ticket counter queue where customers are served in FIFO order using a linked list-based queue implementation.
