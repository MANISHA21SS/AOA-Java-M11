
# EX 1D Sorted Array using Divide and Conquer Approach.
## DATE: 17/04/26
## AIM:
To write a Java program to for given constraints.
Given two sorted arrays nums1 and nums2 of size m and n respectively, return the median of the two sorted arrays.

The overall run time complexity should be O(log (m+n)).

## Algorithm
1.Start the program. Read the sizes of two sorted arrays m and n, then input the elements of both arrays nums1 and nums2.

2.Initialize two pointers p1 = 0 and p2 = 0 to traverse both arrays.

3.Use a helper function getMin() to return the smaller of the current elements from both arrays and move the corresponding pointer forward.

4.Find the median:

If the total number of elements (m + n) is even, skip (m + n)/2 - 1 elements, then take the average of the next two smallest elements as the median.

If (m + n) is odd, skip (m + n)/2 elements, then take the next smallest element as the median.

5.Display the computed median and stop the program.  

## Program:
```
/*

Developed by: Manisha selvakumari.S.S.
Register Number: 212223220055
*/
import java.util.Scanner;

public class Solution {
    private int p1 = 0, p2 = 0;

    // Get the smaller value and move pointer
    private int getMin(int[] nums1, int[] nums2) {
        if (p1 < nums1.length && p2 < nums2.length) {
            return nums1[p1] < nums2[p2] ? nums1[p1++] : nums2[p2++];
        } 
        else if (p1 < nums1.length) {
            return nums1[p1++];
        } 
        else {
            return nums2[p2++];
        }
    }

    // Find median
    public double findMedianSortedArrays(int[] nums1, int[] nums2) {
        int m = nums1.length;
        int n = nums2.length;
        int total = m + n;

        if (total % 2 == 0) {
            for (int i = 0; i < total / 2 - 1; i++) {
                getMin(nums1, nums2);
            }

            int first = getMin(nums1, nums2);
            int second = getMin(nums1, nums2);

            return (first + second) / 2.0;
        } 
        else {
            for (int i = 0; i < total / 2; i++) {
                getMin(nums1, nums2);
            }

            return getMin(nums1, nums2);
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Solution sol = new Solution();

        int m = sc.nextInt();
        int[] nums1 = new int[m];

        for (int i = 0; i < m; i++) {
            nums1[i] = sc.nextInt();
        }

        int n = sc.nextInt();
        int[] nums2 = new int[n];

        for (int i = 0; i < n; i++) {
            nums2[i] = sc.nextInt();
        }

        double median = sol.findMedianSortedArrays(nums1, nums2);
        System.out.println("Median of the two sorted arrays = " + median);

        sc.close();
    }
}
```

## Output:

<img width="1232" height="344" alt="image" src="https://github.com/user-attachments/assets/3b6775de-3209-4991-aa22-96503194aebc" />


## Result:
The program successfully implemented and the expected output is verified.
