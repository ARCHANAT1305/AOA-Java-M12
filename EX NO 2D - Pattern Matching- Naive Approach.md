
# EX 2D Pattern Matching using Naive Approach.
## AIM:
To write a Java program to for given constraints.
Given text string with length n and a pattern with length m, the task is to prints all occurrences of pattern in text.
Note: You may assume that n > m.

Examples: 

Input:  text = "THIS IS A TEST TEXT", pattern = "TEST"
Output: Pattern found at index 10

Input:  text =  "AABAACAADAABAABA", pattern = "AABA"
Output: Pattern found at index 0, Pattern found at index 9, Pattern found at index 12
## Algorithm
1. Start and read the input strings — the main text and the pattern to be searched.
2. Determine the lengths of the text (n) and the pattern (m).
3. Slide the pattern over the text one character at a time from index 0 to n - m. 
4. For each position, compare the pattern with the substring of text character by character.   
5. If all characters match, print the starting index of the match; continue until the entire text is checked, then stop.  

## Program:
#### Developed by: ARCHANA T
#### Register Number: 212223240013 
```
import java.util.Scanner;
public class NaivePatternSearch {
    static void search(String text, String pattern) {
        int n = text.length();
        int m = pattern.length();

        for (int i = 0; i <= n - m; i++) {
            int j;

            // Check for pattern match character by character
            for (j = 0; j < m; j++) {
                if (text.charAt(i + j) != pattern.charAt(j))
                    break;
            }

            // If pattern found
            if (j == m)
                System.out.println("Pattern found at index " + i);
        }
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        //System.out.print("Enter the text: ");
        String text = scanner.nextLine();
        String pattern = scanner.nextLine();
        search(text, pattern);

        scanner.close();
    }
}
```

## Output:

<img width="546" height="183" alt="image" src="https://github.com/user-attachments/assets/8f9a4ff2-90b5-451b-b2e1-5b642660611c" />


## Result:
The program successfully implemented and the expected output is verified.
