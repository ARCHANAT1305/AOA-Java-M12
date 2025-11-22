
# EX 2A Assign Cookies using Greedy Algorithm. 
## AIM:
To Write a Java program for the following Constraints.
Assume you are an awesome parent and want to give your children some cookies. But, you should give each child at most one cookie.

Each child i has a greed factor g[i], which is the minimum size of a cookie that the child will be content with; and each cookie j has a size s[j]. If s[j] >= g[i], we can assign the cookie j to the child i, and the child i will be content. Your goal is to maximise the number of your content children and output the maximum number.

## Algorithm
1. Start and read the number of children n, their greed factors, number of cookies m, and cookie sizes
2. Sort both arrays — greed factors and cookie sizes — in ascending order.
3. Initialize two pointers: one for children and one for cookies.
4. Traverse both arrays, assigning a cookie to a child if the cookie size ≥ the child’s greed factor, then move to the next child.
5. Continue until all cookies or children are checked, then print the total number of satisfied (content) children and stop.

## Program:
#### Developed by: ARCHANA T
#### Register Number: 212223240013
```
import java.util.Arrays;
import java.util.Scanner;
public class AssignCookies {
    public static int findContentChildren(int[] g, int[] s) {
        Arrays.sort(g);
        Arrays.sort(s);
        int childIndex = 0;
        int cookieIndex = 0;
        while (childIndex < g.length && cookieIndex < s.length) {
            if (s[cookieIndex] >= g[childIndex]) {
                childIndex++; 
            }
            cookieIndex++; 
        }
        return childIndex; 
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        int n = scanner.nextInt();
        int[] greedFactors = new int[n];
       
        for (int i = 0; i < n; i++) {
            greedFactors[i] = scanner.nextInt();
        }
        int m = scanner.nextInt();
        int[] cookieSizes = new int[m];
        
        for (int i = 0; i < m; i++) {
            cookieSizes[i] = scanner.nextInt();
        }

        int contentChildren = findContentChildren(greedFactors, cookieSizes);
        System.out.println(contentChildren);

        scanner.close();
    }
}
```

## Output:


<img width="269" height="239" alt="image" src="https://github.com/user-attachments/assets/bcacc96a-4774-4f9f-aa3c-5a8db371b39b" />

## Result:
The program successfully print all the numbers from 1 to N. 
