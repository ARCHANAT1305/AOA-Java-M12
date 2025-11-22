
# EX 2B Jump Game using Greedy Algorithm.
## AIM:
To write a Java program to for given constraints.
You are given an array of integers. Each number represents the maximum number of steps you can jump forward from that position.

You start from the first element (index 0). 
Write a program to find the minimum number of jumps required to reach the last index of the array.

If it is not possible to reach the end, return -1.
## Algorithm
1. Start and read the array size n and its elements into nums[].
2. Initialize reachable = 0 to track the farthest index reachable so far.
3. Loop through the array; if the current index i exceeds reachable, return false (cannot proceed further).
4. Update reachable as the maximum of its current value and i + nums[i], and if reachable reaches or exceeds the last index, return true.
5.After the loop, print whether the last index is reachable and stop.   

## Program:
#### Developed by: ARCHANA T
#### Register Number: 212223240013
```
import java.util.Scanner;
public class JumpGame {
    public static boolean canReachLastIndex(int[] nums) {
        int n=nums.length;
         int reachable = 0;
        for (int i = 0; i < n; i++) {
            if (i > reachable) return false;
            reachable = Math.max(reachable, i + nums[i]);
            if (reachable >= n - 1) return true;
        }
        return true;
    }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt(); // Size of array
        int[] nums = new int[n];
        for (int i = 0; i < n; i++) {
            nums[i] = sc.nextInt(); // Elements of array
        }
        System.out.println("Can reach last index: " + canReachLastIndex(nums));
    }
}

```

## Output:

<img width="553" height="199" alt="image" src="https://github.com/user-attachments/assets/69075a6f-84ec-4143-a552-f8df3e86c405" />


## Result:
The program successfully implemented and the expected output is verified.
