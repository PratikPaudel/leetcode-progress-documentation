# Top Interview 150
## Arrays and Strings

### [Merge Sorted Array](https://leetcode.com/problems/merge-sorted-array/description/)

=== "Hints"

    ```java
    // Compare elements from the end of nums1 and nums2, and place the larger element at the end of nums1.
    // If there are remaining elements in nums2, copy them into nums1.
    // Set pointers to the end of the relevant parts of nums1 and nums2. Also make a pointer on the 'm' value to compare with nums2 values. Pointers at the end of nums1 helps to insert into the appropriate place in nums1.
    ```

=== "Solutions"

    ```java
    int i = m - 1;
    int j = n - 1;
    int k = m + n - 1;
    
    while (i >= 0 && j >= 0) {
      if (nums2[j] > nums1[i]) {
        nums1[k] = nums2[j];
        j--;
      } else {
        nums1[k] = nums1[i];
        i--;
      }
      k--;
    }
    while (j >= 0) {
      nums1[k] = nums2[j];
      j--;
      k--;
    }
    ```

=== "Resources"
    - YouTube

??? summary "Summary"

    To solve the problem of merging two sorted arrays into one sorted array in-place, start by initializing three pointers: one for the end of the initialized part of the first array, one for the end of the second array, and one for the end of the total merged array. Compare the elements at the ends of both arrays and place the larger element at the end of the merged array, moving the respective pointer one position to the left. Repeat this process until one of the arrays is exhausted. If any elements remain in the second array, copy them into the first array.


### [27. Remove Element](https://leetcode.com/problems/remove-element/description/)

=== "Hints"
    ```java
    // Initialize leftPointer to 0 and rightPointer to 0.
    // Traverse the array with rightPointer until it reaches the end of the array:
    // If nums[rightPointer] is equal to val, increment rightPointer to skip this element.
    // If nums[rightPointer] is not equal to val, assign nums[rightPointer] to nums[leftPointer], and increment both leftPointer and rightPointer.
    // Return leftPointer, which represents the new length of the array after removing the elements equal to val.
    ```

=== "Solutions"
    ```java
    int leftPointer = 0;
    int rightPointer = 0;
    while (rightPointer < nums.length) {
      if (nums[rightPointer] == val) {
        rightPointer++;
      } else {
        nums[leftPointer] = nums[rightPointer];
        leftPointer++;
        rightPointer++;
      }
    }
    return leftPointer;
    ```

=== "Resources"
    - YouTube

??? summary "Summary"

    To solve the problem of removing all occurrences of a specified value from an array, initialize two pointers: leftPointer and rightPointer, both set to 0. Use a while loop to traverse the array with rightPointer. If nums[rightPointer] equals the specified value, increment rightPointer to skip it. If nums[rightPointer] is not the specified value, copy nums[rightPointer] to nums[leftPointer], then increment both leftPointer and rightPointer. Continue this process until rightPointer reaches the end of the array. The value of leftPointer at the end of the loop will indicate the number of elements that are not equal to the specified value. The array is modified in place, and the final value of leftPointer is returned as the result.

### [26. Remove Duplicates from Sorted Array](https://leetcode.com/problems/remove-duplicates-from-sorted-array/description)

=== "Hints"
    ```java
    // Initialize leftPointer to 1 and rightPointer to 1.
    // Traverse the array with rightPointer until it reaches the end of the array.
    // If nums[rightPointer] is equal to nums[rightPointer - 1], increment rightPointer to skip this element.
    // If nums[rightPointer] is not equal to nums[rightPointer - 1], assign nums[rightPointer] to nums[leftPointer], and increment both leftPointer and rightPointer.
    // Return leftPointer, which represents the new length of the array after removing duplicates.
    ```

=== "Solutions"
    ```java
    class Solution {
      public int removeDuplicates(int[] nums) {
        int leftPointer = 1;
        int rightPointer = 1;
        while (rightPointer < nums.length) {
          if (nums[rightPointer] == nums[rightPointer - 1]) {
            rightPointer++;
          } else {
            nums[leftPointer] = nums[rightPointer];
            leftPointer++;
            rightPointer++;
          }
        }
        return leftPointer;
      }
    }
    ```

=== "Resources"
    - YouTube

??? summary "Summary"

    To solve the problem of removing duplicates from a sorted array, initialize two pointers: `leftPointer` and `rightPointer`, both set to 1. Use a `while` loop to traverse the array with `rightPointer`. If `nums[rightPointer]` equals `nums[rightPointer - 1]`, increment `rightPointer` to skip it. If `nums[rightPointer]` is not equal to `nums[rightPointer - 1]`, copy `nums[rightPointer]` to `nums[leftPointer]`, then increment both `leftPointer` and `rightPointer`. Continue this process until `rightPointer` reaches the end of the array. The value of `leftPointer` at the end of the loop will indicate the number of unique elements. The array is modified in place, and the final value of `leftPointer` is returned as the result.
