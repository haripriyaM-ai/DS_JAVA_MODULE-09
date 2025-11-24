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
